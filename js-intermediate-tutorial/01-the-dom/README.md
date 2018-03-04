## The DOM

**The Document Object Model** là cách để thao tác structure và style của một trang HTML. Nó đại diện cho bản chất của trang khi browsers thấy nó, và cho phép developer được chỉnh sửa nó với JavaScript
> Nếu bạn muốn xem DOM của một trang, hãy mở developer tools trong browser lên và mở ô "elements". Nó cho thấy một cái nhìn sâu sắc về cách mà browsers nghĩ và hầu hết các browsers cho phép bạn xóa và chỉnh sửa elements trực tiếp. Give it try ^^!

#### Trees and Branches

HTML có cấu trúc tương tự XML trong đó các elements tuân theo cấu trúc giữa các nút cha và con, giống như các nhánh cây. Trong đó với root element là **html** có nhánh con là **head** và **body**, tương tự với các nhánh đó lại có nhánh riêng của nó. Vì vậy mà DOM cũng được gọi là DOM tree.

Thay đổi DOM bằng cách refer đến một element và thay đổi nó. Để truy cập vào DOM từ JavaScript, ta sử dụng đối tượng **document**, được cung cấp bởi browsers.

#### Getting an Element

Điều đầu tiên cần biết là làm thế nào để lấy một element. Có nhiều cách để thực hiện điều này:

##### By ID

**document.getElementById** là phương thức lấy một element qua ID của nó
```
var pageHeader = document.getElementById('page-header');
```
*page-header* element sau đó có thể được thao tác, chẳng hạn thay đổi size, color và khai báo xử lý sự kiện click, hover

##### By Tag Name

**document.getElementsByTagName** là phương thức lấy một element qua tag name (*a, ul, li, etc*). Trả về một **NodeList**, là mảng DOM elements.

##### By Class Name

**document.getElementsByClassName** tương tự như **getElementsByTagName**, nhưng theo class name.

##### By CSS Selector

Một cặp methods tiện lợi khác trong các modern browsers cho phép lấy element dễ dàng hơn qua CSS selectors. 
- **document.querySelector**
- **document.querySelectorAll**

```
var pageHeader = document.querySelector('#header');
var buttons = document.querySelectorAll(.btn);
```
**querySelector** giống như **getElementById**, chỉ trả về một element trong **querySelectorAll** trả về một NodeList. Nếu có nhiều elements mà match với selection bạn truyền vào querySelector, thì element đầu tiên sẽ được trả về.

- Trang kế: [Events and Callbacks]()
- Trang trước: [JavaScript Intermediate Tutorial introduction]()