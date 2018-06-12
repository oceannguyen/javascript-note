# JavaScript Window - The Browser Object Model

The Browser Object Model (BOM) allows JavaScript to "talk to" the browser.

Vì các modern browsers hầu hết implement cùng các methods và properties để tương tác JavaScript, nên nó thường được biết là methods và properties của BOM

## The Window Object

Đối tượng **window** được hỗ trợ biết tất cả các trình duyệt. Nó đại diện cho cửa số trình duyệt.
Các objects, functions, và variables tự động là thành viên của đối tượng window.
```javascript
window.document.getElementById("header");
```
tương đương với
```javascript
document.getElementById("header");
```

## Window Screen

Đối tượng **window.screen** chứa thông tin về màn hình của người dùng.
```javascript
document.getElementById("demo").innerHTML =
"Screen Width: " + screen.width;

document.getElementById("demo").innerHTML =
"Screen Height: " + screen.height;
```

## Window Location

Đối tượng **window.location** có thể dùng để lấy địa chỉ trang hiện tại và redirect trình duyệt đến trang khác.
Ví dụ:
- window.location.href returns the href (URL) of the current page
- window.location.hostname returns the domain name of the web host
- window.location.pathname returns the path and filename of the current page
- window.location.protocol returns the web protocol used (http: or https:)
- window.location.assign loads a new document

## Window History

Đối tượng **window.history** chứa lịch sử của trình duyệt

Để bảo vệ quyền riêng tư của người dùng, có một số giới hạn trong việc JavaScript truy cập vào đối tượng này.

Một số phương thức như:
- history.back() - same as clicking back in the browser
- history.forward() - same as clicking forward in the browser

## Window Navigator

Đối tượng **window.navigator** chứa thông tin về trình duyệt của người dùng.

Ví dụ:
- navigator.appName
- navigator.appCodeName
- navigator.platform

## Popup Boxes

JavaScript có 3 kiểu popup boxes: Alert box, Confirm box, và Prompt box.
```javascript
// alert box
alert("I am an alert box!");

// confirm box
if (confirm("Press a button!")) {
    txt = "You pressed OK!";
} else {
    txt = "You pressed Cancel!";
}

// prompt box
var person = prompt("Please enter your name", "Harry Potter");

if (person == null || person == "") {
    txt = "User cancelled the prompt.";
} else {
    txt = "Hello " + person + "! How are you today?";
}

```