## Events and Callbacks

Trong trình duyệt, hầu hết code là hướng sự kiện việc viết các ứng dụng tương tác trong JavaScript thường là đợi và phản hồi lại sự kiện, để thay đổi hành vi của trình duyệt. Các sự kiện xảy khi load trang, khi người dùng tương tác (clicks, hovers, changes).

Để phản hồi lại sự kiện bạn cần phải lắng nghe và cung cấp một function sẽ được gọi bởi trình duyệt khi sự kiện xảy ra. Function này được gọi là **callback**

Dưới đây là một nhóm những thứ cần để lắng nghe cho một sự kiện; **callback** function, element và lời gọi để lắng nghe sự kiện;
```javascript
// define a callback function
var handleClick = function(event) {
    // do something!
    alert("handling click '#big-button'");
};
// pick an element
var button = document.querySelector('#big-button');
// add listen for click event
button.addEventListener('click', handleClick);
```

```addEventListener``` là một method được thấy trên tất cả các DOM elements. Ở đây nó đang được gọi trên một element được lưu trong biến *button*. Tham số thứ nhất là tên của sự kiện (```click```) tham số thứ hai là **callback** function (```handleClick```).

> Thật không may là, Internet Explorer không hỗ trợ ```addEventListener``` trước version 9. Thay vào đó là:
```
button.attachEvent('onclick', handleClick);
```
> Thêm nữa là nó yêu cầu ```onclick```, không phải ```click```. Do vậy dẫn tới việc phát triển các thư viện như **jQuery** - giúp bạn không phải quan tâm đến cách lắng nghe sự kiện trên các trình duyệt khác nhau

Data là một sự kiện cụ thể được truyền vào **callback**. Quan sát định nghĩa ```handleClick```, có tham số ```event``` là một đối tượng mô tả sự kiện xảy ra với các thuộc tính của nó.

Dưới đây là một sự kiện ví dụ. Có rất nhiều thuộc tính mà đối tượng ```event``` cung cấp như nơi xảy ra sự kiện (```pageX``` và ```pageY```), hay ```target``` cho biết node tham chiếu mà đã được click.
```javascript
{
    offsetX: 74,
    offsetY: 10,
    pageX: 154,
    pageY: 576,
    screenX: 154,
    screenY: 489,
    target: h2,
    timeStamp: 1363131952985,
    type: "click",
    x: 154,
    y: 395
}
```
