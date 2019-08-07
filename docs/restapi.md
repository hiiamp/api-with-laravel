# REST API

Bài viết ở mục trên đã trình bày một cách khá tổng quan về API, ở đây chúng ta sẽ đi tìm một "kiểu" API được sử dụng rộng rãi và phổ biến hiện nay, đó chính là REST API.

## REST - REpresentational State Transfer

Trước khi đi vào định nghĩa của REST API, hãy tìm hiểu thêm một chút về REST để có thể dễ dàng tiếp cận hơn các vấn đề sau này.

REST(REpresentational State Transfer) là một kiến trúc phần mềm phổ biến nhất hiện nay trên internet. Để đơn giản, ta có thể hiểu nó là một tập hợp gồm các ràng buộc và quy ước, một hệ thống khi tuân theo tất cả những vấn đề trên thì được gọi là một hệ thống REST.

Vậy bây giờ có vẻ mọi thứ đã đơn giản hơn khi nói về REST API. Đơn giản nó là một loại API tuân thủ theo kiến trúc REST.

### REST Constraint

Ở trên đã nói qua một chút về REST, phần này chúng ta sẽ điểm qua một số ràng buộc đáng chú ý nhất về REST(không phải tất cả).

* Client - (Cache) - Server: Đây là mô hình mà một hệ thống REST sử dụng.
Trong đó server là tập hợp các service nhỏ lắng nghe các request từ client. Với từng request khác nhau thì có thể một hoặc nhiều service xử lý. Ở giữa chúng, REST cho phép khả năng caching, tức là các response có thể lấy ra từ cache để tăng tốc độ của hệ thống.
* Stateless (Phi trạng thái): Server và client sẽ không lưu trạng thái của nhau.
Điều này giúp hệ thống dễ phát triển, bảo trì và mở rộng vì không tốn công CRUD trạng thái của client nhưng nó đòi hỏi mỗi request gửi lên server thì client phải đóng gói thông tin đầy đủ để server có thể hiểu được. Việc làm trên cũng mang đến một nhược điểm là gia tăng lượng thông tin cần truyền tải giữa client và server.
* Chuẩn hóa interface: Đây là một đặc tính quan trọng của REST, nó đặt ra một số các quy ước chuẩn để giao tiếp giữa các thành phần trong hệ thống, giúp cho việc sử dụng hệ thống trở nên đơn giản và dễ dàng. Đặc biệt rất hữu ích vì mọi nền tảng dù là mobile, web đều có thể dễ dàng sử dụng các API có chuẩn này. Tuy nhiên vì viết cho đa nền tảng nên mỗi kết nối rất khó có thể tối ưu được sau khi đã chuẩn hóa.
* Phân lớp hệ thống : trong hệ thống REST bạn chia tách các thành phần hệ thống theo từng lớp, mỗi lớp chỉ sử dụng lớp ở dưới nó và giao tiếp với lớp ở ngay trên nó mà thôi. Điều này giúp bạn giảm độ phức tạp của hệ thống,giúp các thành phần tách biệt nhau từ đó dễ dàng mở rộng từng thành phần.

### Resources

REST đặt ra một quy tắc đòi hỏi lập trình viên xác định rõ ý định của mình thông qua các phương thức của HTTP. Thông thường ý định đó bao gồm lấy dữ liệu, trèn dữ liệu, cập nhập dữ liệu hoặc xóa dữ liệu. Vậy khi bạn muốn thực hiện một trong các ý định trên hãy lưu ý các quy tắc sau:

* Để tạo một tài nguyên trên máy chủ, bạn cần sử dụng phương thức POST.
* Để truy xuất một tài nguyên, sử dụng GET.
* Để thay đổi trạng thái một tài nguyên hoặc để cập nhật nó, sử dụng PUT.
* Để huỷ bỏ hoặc xoá một tài nguyên, sử dụng DELETE.

Chú ý rằng các nguyên tắc ở trên là không bắt buộc, thực tế bạn có thể sử dụng phương thức GET để yêu cầu lấy dữ liệu, trèn, sửa hoặc xóa dữ liệu trên Server. Tuy nhiên REST đưa ra các nguyên tắc ở trên mục đích đưa mọi thứ trở lên rõ ràng và dễ hiểu.

## Kết luận

Đến đây, chúng ta đã định hình được một API theo chuẩn REST là như thế nào. Phần sau tôi sẽ tiếp tục giới thiệu đến các bạn cách để xây dựng API dựa trên framework của php là laravel.

