### jQuery: AJAX

jQuery có một số phương thức tiện ích cho AJAX nhằm tiết kiệm thời gian và dễ đọc hơn. Chúng là các thuộc tính của biến ```**$**```: ```$.get```, ```$.post```, ```$.put``` và ```$.ajax```

```$.ajax``` là phương thức chính, cho phép bạn dựng AJAX phù hợp request, các phương thức kia chỉ là cú pháp ngắn gọn hơn như get, put

Đây là ví dụ lấy dữ liệu từ server:

```javascript
$.ajax({
    url: './data.json',
    method: 'GET',
    success: function(data) {
        console.log(data);
    }
});
```
Bạn có thể thấy rằng đối tượng trên dùng để yêu cầu jQuery làm thế nào để lấy dữ liệu. Những thông tin cơ bản như: URL, method (mặc định là ```get```) và một hàm sẽ được gọi khi dữ liệu được trả về, được gọi là **success callback**

### $.get

Ví dụ lấy dữ liệu là method phổ biến nên jQuery cung cấp: ```$.get```
```javascript
$.get('/data.json', function (data) {
    console.log(data);
});
```
Bạn cũng có thể cung cấp error callback, cho bạn biết nếu lỗi xảy ra:
```javascript
$.get('/data.json', function (data) {
    console.log(data);
}).fail(function () {
    // Uh oh, something went wrong
});
```

### $.post

Gửi dữ liệu đến server đơn giản với phương thức ```$.post```. Tham số thứ 2 chỉ định dữ liệu sẽ được gửi.
```javascript
$.post('/save', { username: 'tom' }, function (data) {
    console.log(data);
}).fail(function () {
    // Uh oh, something went wrong
});
```

### $.ajax

Tất nhiên, nếu bạn muốn kiểm soát nhiều hơn với dữ liệu, bạn có thể sử dụng ```$.ajax```

```javascript
$.ajax({
    url: '/save',
    method: 'POST',
    data: { username: 'ocean' },
    success: function(data) {
        console.log(data);
    }
    ,
    error: function() {
        // Uh oh, something went wrong
    }
});
```
