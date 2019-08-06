# API - Application Programming Interface

## API là gì?

API là viết tắt của Application Programming Interface (giao diện lập trình ứng dụng) phương thức kết nối với các thư viện và ứng dụng khác.

Định nghĩa trên có vẻ hơi tổng quát và khó để có thể nắm bắt được rõ ràng về API. Những phần sau sẽ cố gắng làm rõ hơn vấn đề này.

## Hai kiểu kiến trúc trong xây dựng ứng dụng và những vấn đề liên quan

Những ngày trước, đa phần các dự án được viết theo kiến trúc `Monolithic`, với kiểu mô hình như sau:

<p align="center">
	<img src="/image/api2.jpg" />
</p>

Hiểu đơn giả, kiến trúc `Monolithic` là kiểu "kiến trúc một khối", tức là đa phần các xử lý được thực hiện kết hợp, móc nối chặt chẽ với nhau.

Với những dự án đơn giản, kiến trúc này có rất nhiều lợi thế khi làm cho quá trình development đơn giản và trực tiếp hơn, tất cả quá trình development cũng thống nhất với nhau chặt chẽ. Mọi thứ có vẻ vẫn rất tốt đẹp.

Tuy nhiên khi gặp phải những dự án lớn, kiến trúc này gặp phải vấn đề đó là nó quá khó khăn trong việc bảo trì, quá trình phát triển vì liên kết chặt chẽ với nhau quá nhiều nên mất đi tính linh hoạt cần thiết. Đi kèm với đó, tính ổn định của dự án cũng không cao vì nếu có một vấn đề xảy ra, cả hệ thống sẽ bị crash theo. Đây chính là vấn đề đầu tiên.

Vấn đề thứ hai, với cách xây dựng như trên, khi chúng ta tạo ra một dự án đa nền tảng, thì mỗi nền tảng lại phải được development một cách riêng biệt với nhau, quá mất thời gian và công sức.

Một vấn đề nữa là nếu như có một bên thứ ba muốn sử dụng một hoặc một vài thành phần, tính năng trong dự án của chúng ta thì rất khó giải quyết và mất thời gian. Ví dụ như một bên thứ ba nào đó muốn thêm nút like của facebook vào cho ứng dụng của họ chẳng hạn.

Vậy thì để giải quyết các vấn đề trên bằng cách nào? Câu trả lời là sử dụng một kiến trúc khác, đi ngược lại tư tưởng của kiến trúc `Monolithic` ở trên, đó là kiến trúc `Microservice`.

Kiến trúc `Microservice` đề cập đến quá trình phát triển độc lập, tương đối nhỏ theo hướng chia hệ thống ra thành các service. Mỗi service này đều có một logic riêng, một trách nhiệm riêng và có thể được deploy riêng biệt.

Có thể dễ dàng thấy được, với kiểu kiến trúc này, tất cả vấn đề trên đều được giải quyết một cách ổn thõa khi mỗi service đều độc lập với nhau và tất nhiên là việc thay đổi mỗi service đó sẽ đơn giản hơn so với kiểu kiến trúc trước kia.

## Tại sao phải có API?

Vậy những vấn đề "lan man" được đề cập phía trên có liên quan gì đến API?

Thực ra, những dự án được xây dựng từ API thì "có thể xem như là" tuân theo kiến trúc `Microservice`. Tức là mỗi API sẽ đảm nhiệm một nhiệm vụ riêng biệt, và tập hợp các API cần thiết sẽ tạo nên một hệ thống hoàn chỉnh (hmmm ..., có vẻ là về hướng backend mà thôi).

Mỗi API sẽ có một quy chuẩn riêng về `input` , `output` tương ứng và những vấn đề xung quanh quá trình hoạt động để dev hoặc bên thứ ba hay người dùng có thể sử dụng mà không cần quan tâm API đó đã giao tiếp với hệ thống như thế nào. Chỉ cần xem qua tài liệu đặc tả API thì mọi thứ sẽ trở nên đơn giản với mọi người (có thể).

## Kết luận

Vậy tóm lại, API là một thành phần, một service đảm nhận một nhiệm vụ nào đó mà qua đó chùng ta có thể  thiết kế, giao tiếp, sử dụng được với ứng dụng một cách dễ dàng mà không cần nắm rõ cấu trúc bên trong hệ thống (đúng với nghĩa `interface`).