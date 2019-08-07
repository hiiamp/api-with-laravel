# Xây dựng API với Laravel

Sau khi tìm hiểu chung về API cũng như một kiểu API phổ biến hiện nay là REST API, bài viết này sẽ hướng dẫn chúng ta xây dựng một `REST API` đúng chuẩn với `framework laravel` version 5.7.

Nếu chưa nắm bắt được về framework phổ biến này, bạn có thể tìm hiểu thêm về nó [tại đây](http://laravel.com.vn/docs/5.7).

## HTTP Request

Ở phần trước, tôi đã trình bày sơ lược về HTTP Request, tuy nhiên đễ có cái nhìn rõ hơn và thuận tiện trong việc xây dựng API, chúng ta hãy cùng tìm hiểu qua một lần nữa về nó.

HTTP Request có tất cả 9 loại method, 2 loại được sử dụng phổ biển nhất là `GET` và `POST`.

```
GET: được sử dụng để lấy thông tin từ sever theo URI đã cung cấp.
HEAD: giống với GET nhưng response trả về không có body, chỉ có header
POST: gửi thông tin tới sever thông qua các biểu mẫu http (đăng kí chả hạn ...)
PUT: ghi đè tất cả thông tin của đối tượng với những gì được gửi lên
PATCH: ghi đè các thông tin được thay đổi của đối tượng.
DELETE: xóa tài nguyên trên server.
CONNECT: thiết lập một kết nối tới server theo URI.
OPTIONS: mô tả các tùy chọn giao tiếp cho resource.
TRACE: thực hiện một bài test loop - back theo đường dẫn đến resource.
```

## Router RESTful

Bây giờ hãy áp dụng các method của `HTTP request` trình bày ở trên vào `router` của `laravel`.

Để phân biệt rõ ràng giữa các loại router, laravel đã tạo sẵn nhiều file routes khác nhau. Vì ta đang đi viết api nên sẽ sử dụng file `routes/api.php` để khai báo router thay vì `routes/web.php`.

Laravel có một số setting mặc định cho file `api.php` này, hãy xem qua một chút để tránh các vấn đề phát sinh sau này:

* Url: những `router` được khai báo trong file này mặc định có `prefix url` là "api" (Ví dụ: [mysite.me/api/firstapi](#)).
* Middleware: Được mặc định gán `Middleware Group: api`. Có thể tìm thấy 2 `middleware` thuộc nhóm này là `throttle` (giới hạn request/time) và `bindings` (model binding) trong file `app\Providers\RouteServiceProvider.php`.

Những setting mặc định này có thể được tùy chỉnh trong method `mapApiRoutes` trong file `app/Providers/RouteServiceProvider.php`.
