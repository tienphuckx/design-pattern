SAGA có 2 Pattern chính


## 1. Choreography (Hợp tác nhưng phân tán) 
    - Mỗi node tự xử lý các giao dịch và thông báo kết quả bằng EVENT. 
    - Apply Message Brocker (Người đưa thư) đứng ở giữa để quản lý các EVENT mà các Service tạo ra/ lắng nghe.
    - Mỗi giao dịch sẽ được định danh bằng mỗi ID khác nhau.

## 2. OrChestration (Điều phối tập trung)
    - Cần Build một Service điều phối ở trung tâm điều khiển các node tuần tự hoàn thành giao dịch.
    - Ưu điểm: dễ quản lý và tracking giao dịch.
    - Nhược điểm: quản lý tập trung nên dễ bị nghẽn cổ chai (bottleneck)
    - Không cần thiết sử dụng Message brocker nhưng cũng có thể apply.

    EXAMPLES of Choreography

    - NotificationService
    - BasketService
    - OrderingService
    - PaymentService
    - ShippingService

* Mỗi Service sẽ handle một tác vụ trong một chuỗi hành đông (Đặt hàng)
    mỗi service sau khi hoàn thành một tác vụ
    sẽ bắn notify/event
    các service liên quan sẽ lắng nghe event và nối tiếp hành động.

    + Checkout (BasketService): tạo/lưu đơn hàng và notify cho (OrderingService) để tạo chi tiết đơn hàng 
    + OrderingService : Validate/Check create order và thành công / thất bại tạo ra event/notify
    + PaymentService : Tương tự, xử lý thanh toán
        - success: notify to ShippingService
        - fail: notify to OrderingService
    + ShippingService:

## Khi nào nên sử dụng SAGA
* SAGA trong văn học nghĩa là một câu chuyện dài.
    - Khi hệ thống có nhiều dịch vụ microservice hoạt động độc lập
    - Cần xử lý các giao dich phân tán, không đồng bộ.
    - Tăng khả năng phục hồi lỗi và linh hoạt trong việc hoàn tác giao dịch (các tác vụ có yếu tố hoàn tác cao: trả hàng, hoàn tiền, ...)
