# TOP
- khi ứng dụng ngày càng phức tạp hơn, nếu code không theo nhưng khuôn mẫu, thiết kế  thì sẽ ngày càng trở nên phức tạp và khó hiểu.
- SOLID ra đời - 5 nguyên tắc thiết kế:
    
    ## 1. Single Responsibility Principle (SAP)
        - Mỗi Class chỉ nên thay đổi vì 1 lý do
        - Mỗi Class chỉ chịu trách nhiệm cho một chức năng duy nhất
        -> Dễ hiểu, dễ bảo trì và phát triển.

        Ex:
            WRONG:
                Class User {
                    saveUser()
                    sendEmailToUser() XXXXX
                }
                    
            
            CORRECT:
                Class User
                    saveUser()

                Class EmailService {
                    sendEmailToUser()
                }

        Rs:
            - Khi đã tách riêng ra thì mỗi mudun con chỉ chịu trách nhiệm mỗi nhiệm vụ cụ thể, làm cho code dễ đọc dễ hiểu và dễ bảo trì hơn
            - Ngoài ra còn cung cấp khả năng gọi và tái sử dụng ở những Service khác cần tới.

    ## 2. Open/Close Principle (OCP)
        - Hạn chế sửa đổi
        - Ưu tiên mở rộng
        * Khi có một modun, function cần thay đổi update cho một luồng mới, tính năng mới thì ưu tiên viết mới luồng đó thay vì sửa đổi trên code cũ.
        -> để tránh bị ảnh hưởng tới các behavior khác đang hoạt động, làm tăng độ phức tạp và phải huy động testing full cases.

    ## 3. Liskov Substitution Principle (LSP)
        - Các Class con phải có thể thay thế được Class Cha
        mà không làm thay đổi tính đúng đắn của chương trình.

        Ex.
            FALSE
                class Bird {
                    fly()
                }
                class Penguin extend Bird {  // WRONG
                    // but penguin can't fly 
                }

            TRUE
                class Bird {}
                class FlyingBird extends Bird {
                    fly();
                }
                class Penguin extend Bird { // OK}

    ## 4. Interface Segregation Principle (ISP)
        - Một Class không nên bị phụ thuộc vào các interface mà nó không sử dụng.
        - Nên chia nhỏ thành các interface với những ý nghĩa riêng của nó.
        (Thay vì tạo 1 interface lớn cho một service impl)

        Ex. Account Service 

        - WRONG:
            Account() {
                pay() // thanh toán bình thường
                pay_first_even_0usd() -> thẻ tín dụng có thể trả trước
            }

        - CORRECT:
            AccountBase(){
                pay() // thanh toán bình thường 
            }
            AccountTinDung extend AccountBase(){
                pay_first_even_0usd() //TINDUNG
            }

    ## Depenancy Inversion Principle (DIP)
        - Các modun cấp cao, không nên phụ thuộc vào các modun cấp thấp
        mà chỉ nên phụ thuộc vào Abstract
        --> Dễ bảo trì và mở rông

        Ex.
            - WRONG:
                EmailService(){}
                NotifyService(){
                    constructor(){
                        New EmailService() --> Phụ thuộc vào Email service
                    }
                    notify(){
                        EmailEervice.sendEmai()
                    }
                }

            - CORRECT
                // Có nhiều Service khác nhau:

                MailService(){}
                SMSService(){}
                ...

                // Module cấp cao notify
                Notify(){
                    constructor(service){
                        this.service = service;
                    }
                    notify(){
                        this.service.send()
                    }
                }

                //Use
                const emailNotify = new Notify(new EmaiService())
                const smsNotify = new Notify(new SMSService())
                
                emailNotify.send()
                smsNotify.send()