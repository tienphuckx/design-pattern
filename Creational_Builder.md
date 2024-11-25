## BUILDER

class Car {
    ...
}

Nếu bạn có một class Car như trên, bạn sẽ có bao nhiêu properties ? 50 or 200?
Và khi đó Constructor sẽ như sau:
    Car car = new Car(color, ................);
-> Rất khó đển maintain và dẫn đến sai sót.

Apply Builder:
    Car and CarBuilder
    Car car = new CarBuilder
                        .color("red")
                        .heihgt("1.5")
                        ...
                        .build()
Bây giờ khởi tạo một Car Object rất tường minh và dễ sử dụng.