## jQuery

Vì yêu tố lịch sử của browser mà khi ta modify hay control DOM trên một trang ta phải sử dụng các tool/cách thức khác nhau cho tương thích với browser chạy ứng dụng. Do vậy mà việc phát triển các thư viện được nảy sinh ra nhằm tạo ra một chuẩn/cách đồng nhất để tương tác với DOM. Thường các thư viện đó cũng cung cấp chức năng cho AJAX để giảm đi sự phức tạp.

**jQuery** là thư viên DOM phổ biến nhất được sử dụng trên nhiều websites hiện nay.

> Tiện đây, cách mà bạn tương tác với DOM (hoặc các service mà bạn sử dụng trong code) được gọi là Application Programming Interface /API

jQuery sử dụng cú pháp rất đặc biệt, tất cả đều xoay quanh ký hiệu **dollar**.
Ví dụ:
```
$('.btn').click(function () {
    // do something
});
```
Đoạn mã trên sẽ xử lý sự kiện 'click' cho các elements có class là '.btn'. Đây là cú pháp selector cơ bản của jQuery.

jQuery được thêm vào trang bằng cách nhúng một file sử dụng thẻ ```script```. [Download jQuery](http://jquery.com/download/) hoặc nhúng nó jQuery từ Content Delivery Network (CDN) như [CDNJS](https://cdnjs.com/)
```
<script src="http://cdnjs.cloudflare.com/ajax/libs/jquery/1.9.1/jquery.min.js"></script>
```
Trong phần tiếp theo bạn sẽ tìm hiểu jQuery cho việc chọn và thao tác elements, AJAX và một số thủ thuật khác.

>Không phải lúc nào cũng là ý tưởng tốt nhất để sử dụng thư viện và nó chỉ tốt khi sử dụng trong dự án cụ thể. VD: Đối với mobile browsers, jQuery là một file lớn do vậy làm chậm việc tải trang và tiềm ẩn các kết nối yếu.