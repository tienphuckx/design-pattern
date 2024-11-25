SAGA có 2 Pattern chính


## 1. Choreography (Hợp tác nhưng phân tán)
## 2. OrChestration (Điều phối tập trung)

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
