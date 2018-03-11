## jQuery: Other Tricks

jQuery cũng giúp bạn với các tác vụ phổ biến khác, đặc biệt chúng thường không thống nhất qua các trình duyệt

### DOMContentLoaded

Đôi khi bạn muốn chạy JavaScript chỉ khi nào DOM đã được load và sẵn sàng (*but before stylesheets are fully loaded)* - ví dụ, để di chuyển elements đến ví trị khác. Bạn có thể chạy đoạn mã JavaScript thuần sau (nó có thể sẽ không hoạt động trên tất cả các trình duyệt):

```javascript
var doSomething = function (event) { . . . };

window.addEventListener('DOMContentLoaded', doSomething);
```
Nhưng bạn có thể thực hiện điều này dễ dàng hơn với jQuery và nó sẽ hoạt động qua mọi trình duyệt:
```javascript
$(window).ready(doSomething);
```
Còn có thể ngắn hơn nữa:
```javascript
$(doSomething);
```
Trong ví dụ trên ```doSomething``` là một hàm.

### Load

Trong các trường hợp khác sẽ tốt hơn khi đợi cho trang được load đủ - đó là khi các stylesheets và images đã được download.

Để làm thể mà không dùng jQuery, lắng nghe sự kiện load trên window như sau:
```javascript
window.addEventListener('load', doSomething);
```
Nhưng với jQuery dễ dàng hơn:
```javascript
$(window).load(doSomething);
```
### Type checking

Tìm ra kiểu dữ liệu đang lưu trữ trong biến JavaScript là điểm khó chịu nhất, vì vậy jQuery cung cấp một số tools hỗ trợ:

```javascript
$.isArray([1, 2, 3]);
```

```javascript
$.isFunction(function () { });
```

```javascript
$.isNumeric(10);
```

```javascript
$.isPlainObject({ name: 'Tom' });
```

