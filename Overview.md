Đứng trên vai người khác các bạn sẽ thấy xa hơn
Design là các thử nghiệm và thành công của các người đi trước
Chúng ta sẽ kế thừa và phát huy các khai phá của họ
Nó là các phương án thiết kế

# 3 nhóm Design Pattern

## 1. CREATIONAL
    - Các Pattern này giải quyết vấn đề khởi tạo đối tượng một cách linh hoạt, thay vì khởi tạo trực tiếp bằng từ khóa new. Giúp tăng tính mềm dẻo và tái sử dụng code.

### 1.1 Singleton
    - Đảm bảo chỉ có duy nhất một instance của một class trong toàn bộ chương trình.
### 1.2 Factory Method
    - Định nghĩa một interface để tạo các đối tượng trong superclass nhưng cho phép lớp con quyết định instance nào sẽ được tạo.
### 1.3 Abstract Factory
    - Cung cấp một interface để tạo ra các họ đối tượng liên quan hoặc phụ thuộc lẫn nhau.
### 1.4 Builder
    - Tách biệt quá trình khởi tạo đối tượng phức tạp khởi các đại diện của nó
### 1.5 Prototype
    - Tạo ra các đối tượng dựa trên một mẫu đối tượng ban đầu

## 2. STRUCTURAL
    - Các Pattern này giải quyết vấn đề cấu trúc và mối quan hệ giữa các thành phần trong phần mềm để tối ưu hóa tính linh hoạt, bảo trì và tái sử dụng.
    - Structural Patterns liên quan đến cấu trúc và mối quan hệ giữa các lớp và đối tượng nhằm tạo ra cấu trúc phần mềm dễ thay đổi và bảo trì hơn.

### 2.1 Adapter
    - Cho phép giao tiếp giữa các interface không tương thích

### 2.2 Bridge
    - Tách rời một lớp phức tạp thành hai phần riêng biệt: trừu tượng và triển khai.

### 2.3 Composite
    - Tạo ra cấu trúc cây để biểu diễn mối quan hệ whole-part giữa các đối tượng.

### 2.4 Decorator
    - Dynamically thêm chức năng mới cho đối tượng mà không ảnh hưởng đến các đối tượng khác.

### 2.5 Facade
    - Cung cấp một giao diện đơn giản cho một nhóm các lớp phức tạp.

### 2.6 Flyweight
    - Sử dụng chia sẻ để hỗ trợ tao hàng loạt các đối tượng hiệu quả hơn.

### 2.7 Proxy
    - Đại diện cho một đối tượng khác để kiểm soát truy cập vào đối tượng đó.

## 3. BEHAVIORAL
    - Behavioral Patterns liên quan đến cách giao tiếp và trao đổi thông tin giữa các đối tượng và lớp. 

### 3.1 Chain of Responsibility
    - Cho phép chuyển các yêu cầu dọc theo chuỗi các đối tượng xử lý.

### 3.2 Command
    - Đóng gói yêu cầu thành các đối tượng có thể tham số hóa

### 3.3 Iterator
    - Truy cập tuần tự các phần tử một tập hợp dữ liệu

### 3.4 Mediator
    - Định nghĩa một đối tượng trung gian để giao tiếp giữa các đối tượng.

### 3.5 Memento
    - 

### 3.6 Observer
    - Định nghĩa phụ thuộc một chiều giữa các đối tượng

### 3.7 State
    - Cho phép một đối tượng thay đổi hành vi dựa trên trang thái nội bộ

### 3.8 Strategy
    - Định nghĩa tập các thuật toán có thể thay thế cho nhau để giải quyết một vấn đề.

### 3.9 Template Method
    - Định nghĩa bố cục xử lý chung cho một thuật toán, hoãn lại các bước cụ thể cho lớp con.

### 3.10 Visitor
    - Tách biệt các thuật toán khởi các đối tượng mà chúng hoạt động trên đó.