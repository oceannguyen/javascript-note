## AJAX

Trong những năm đầu phát triển web, để lấy nội dung mới trên một trang (bài viết, thông báo) bạn phải reload trang hoặc link trang tới khác. Rõ ràng điều này là không cần thiết phải để lấy một nội dung mới, vì việc reload lại trang rất thương tốn thời gian và chi phí khi ứng dụng lớn dần.

Để đạt được điều này, có một tool gọi là ***XML HTTP Request*** được sử dụng. Và các ứng dụng web mà sử dụng tool này được gọi là ***AJAX (Asynchronous JavaScript and XML) apps***

Hầu hết tất cả các trang kéo nội dung mới về mà không phải reload lại trang (Facebook, Gmail, Google Maps etc) đều sử dụng kỹ thuật như nhau. ***XMLHttpRequest*** được tạo ra bởi Microsoft khi phát triển Outlook Web Access

### XML HTTP Request

***XMLHttpRequest*** trông như thế nào?
```javascript
var req = new XMLHttpRequest();
req.onload = function(event) {
    // do something
};
req.open('get', 'http://localhost:8080/ocean/cinema/categories/api/v1/citys', true);
req.send();
```
Đầu tiên cần tạo một ***XMLHttpRequest***, sử dụng từ khóa new, và gọi ***XMLHttpRequest*** giống như function

Sau đó chỉ định một callback function sẽ được gọi khi dữ liệu được load về. Nó truyền thông tin về event vào tham số đầu tiên.

Tiếp theo chỉ định cách mà ta muốn lấy dữ liệu sử dụng ```req.open```. Tham số thứ nhất là HTTP method(GET, POST, PUT, etc). Tham số thứ 2 là URL để lấy dữ liệu. Tham số thứ 3 chỉ định liệu request là bất đồng bộ (***asynchronous***) - true, ***XMLHttpRequest*** được gửi đi HttpRequest tới Server và sau đó đoạn mã khác vẫn tiếp tục được thực thi cho đến khi response từ Server gửi về thì callback function được kích hoạt.

![alt text]:(https://github.com/oceannguyen/javascript-note/edit/master/js-intermediate-tutorial/03-ajax/pic_ajax.png)

Tham số ***asynchronous*** mặc định là false, do vậy khi thực thi code sẽ bị dừng lại cho đến khi dữ liệu được trả về từ Sever request - đây được gọi là synchronous (thường không được sử dụng). 

> Sử dụng XMLHttpRequest bạn có thể load HTML, JSON, XML và plain text qua HTTP và HTTPS, nó cũng hỗ trợ các giao thực khác nữa như FTP và file. Nhìn chung, chúng rất hữu ích cho toàn bộ các tác vụ khi phát triển JavaScript apps.

### AJAX and Libraries
Kỹ thuật AJAX được phát triển cho đến mức bây giờ sinh ra các ứng dụng gọi là Single Page Applications.
