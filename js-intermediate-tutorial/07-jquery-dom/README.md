## jQuery: DOM API

Chọn elements và tương tác với DOM là những thứ mà bạn sẽ sử dụng jQuery nhiều nhất. Thật may mắn là nó rất dễ dàng, vì cú pháp chọn element hoặc tập các elements giống như việc chọn element trong CSS.

jQuery cũng tạo cho việc thực hiện các hành động trên nhiều elements đơn giản cùng một lúc, điều này rất chi là hữu dụng.

Trong ví dụ dưới đây ```$('.note')``` chọn các elements có class là ```note``` trên trang và sau đó set giá trị background cho ```note``` thành màu đỏ và height là 100px.

```javascript
$('.note').css('background', 'red').height(100);
```
jQuery sử dụng cú pháp xâu chuỗi kết nối (neat chainable syntax) cho phép ta viết mã như trên. Bởi vì, với bất cứ phương thức cài đặt nào, *jQuery returns the same thing as the selector function (“$”) does: $ is a function that returns a jQuery wrapper around an element*.

### Getters and setters

Ví dụ ở trên sử dụng ```.css``` và ```.height``` để set giá trị của element, nhưng methods trên cũng là **getters**. 
```javascript
var currentHeight = $('.note').height();
var currentColor = $('.note').css('color');
```
Nếu như bạn có nhiều hơn một element được chọn thì element đầu tiên sẽ được chọn.

### Context

Đôi khi rất hữu ích khi ta giới hạn vùng DOM để chọn element. *The area of the DOM used is also known as a different* context.

Để yêu cầu jQuery nơi nào bạn muốn chọn, bạn truyền tham số thứ 2: có thể là **DOM element**, **string selector** hoặc **jQuery object**. jQuery sẽ tìm kiếm trong phạm vi context đó theo sự lựa chọn của bạn.

Dưới đây là ví dụ. Chú ý rằng các biến mà dùng để lưu jQuery objects bắt đầu với **dollar**. Quy ước này giúp bạn và người đọc code của bạn hiểu rằng đó là một jQuery object.

```javascript
var $header = $('header');
var $headerBoxes = $('.note', $header);
```



