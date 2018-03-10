## JSON

JSON - JavaScript Object Notation là một các quy tắc định dạng văn bản để lưu trữ và chuyển đổi dữ liệu trong máy và theo cách mà con người có thể đọc được. Nó trông giống như cú pháp JavaScript ở dạng chuỗi (JSON bắt nguồn từ đó).

Nhưng JSON không là JavaScript. Nó là một ngôn ngữ khác biệt với các thông số riêng, nó đóng vai trò lớn trong phát triển JavaScript

Ví dụ về JSON:
```javascript
{ "name": "Yoda", age: 894, "lightsaber" : { "color": "green" } }
```

JSON được dùng để chuyển thông tin - giữa browser/client và server. Bạn có thể lưu trữ các dữ liệu phức tạp như objects, arrays, strings, numbers

JSON đang tiếp nhận từ XML là định dạng chuyển đổi dữ liệu của web, và nhiều các web APIs được viết để trả về JSON (bạn có thể sử dụng công nghệ AJAX để lấy JSON).

### Sử dụng JSON

Chuyển dữ liệu sang JSON string, sử dụng method ```stringify```
```javascript
var jsonString = JSON.stringify({
    make: "McLaren",
    model: "MP4-12C",
    miles: 5023
});
```
Sau khi chuyển đối tượng JSON string, được kết quả ```{"make": "McLaren", "model": "MP4-12C", "miles": 5023 }```

Chuyển JSON string sang JSON object, sử dụng method ```parse```
```javascript
{"make": "McLaren", "model": "MP4-12C", "miles": 5023 }
```
Chuỗi có thể chuyển thành đối tượng JavaScript sử dụng ```JSON.parse.car```
```javascript
car.model = "P1";
```

