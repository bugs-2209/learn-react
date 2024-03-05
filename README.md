<h1> Lession 1: Những lưu ý trong ReactJS </h1>
<li>StrictMode: Dùng để tránh những trường hợp không khai báo nhưng vẫn sử dụng</li>
<li>JSX: Được viết tắt của Javascript Extension (JSX là 1 ngôn ngữ)</li>
<li>Mỗi 1 thẻ div, h1, h2, h3,... đều là 1 component của ReactJS</li>
<li>Khi viết trực tiếp style ở thẻ "div" phải viết các thuộc tính theo dạng camelCase và viết theo dạng obj: style: {{ color: "red", backgroundColor: "green" }}</li>
<li>Các tên sự kiện cũng được viết theo dạng camelCase: onClick, onChange,...</li>
<li>Khi truyền function vào các sự kiện thì chỉ truyền tên function và không có "()"</li>

### Ví dụ 1: Không có tham số truyền vào

```
    let handleOnClick = () => {
        console.log("abc");
    }
    <button onClick={handleOnClick}>Click</button>
```

<li>Nếu truyền thêm "()" thì function sẽ tự động thực thi trước khi thao tác event</li>

### Ví dụ 2: Nếu có tham số truyền vào
```
    let handleOnClick = (name) => {
        console.log("abc");
    }
    <button onClick={() => handleOnClick("Bug")}>Click</button>
```
  

<li>Nếu muốn bọc 2 div vào nhau thì sử dụng React.Fragment</li> 
<h3>Ví dụ in 1 list table: </h3>

```
    <div>Hello</div>
    <li>Nguyen Van A</li>
    <li>Nguyen Van B</li>
    <li>Nguyen Van C</li>

    // Coding Example
    import './App.css';

    function App() {
        return (
            <div className="App">
            Hello
            <UserList />
            </div>
        );
    }

    export default App;


    function UserList() {
        return (
            <>
                <li>Nguyen Van A</li>
                <li>Nguyen Van B</li>
                <li>Nguyen Van C</li>
            </>
        );
    }

    export default App;
```

### React có 2 loại Component :

<ul>
    <li>Class Component</li>
    <li>Function Component</li>
</ul>

### Props :

<ul>
    <li>Giống attribute của HTML</li>
    <li>Chỉ có thể xem(get) data chứ không thể sủa(edit)-> immutable. Nếu thay đổi thì chỉ thay đổi từ đầu khi khai báo component</li>
    <li>Truyền data từ thằng cha xuống thằng con</li>
    <li>props.children được khai báo giữa 2 thẻ component</li>
</ul>

<h4>Ví dụ khai báo và sử dụng Prop.Children</h4>
``` 
function App() {
        return (
            <Person fullname="Nguyen Van A" age="28" />
            <Person fullname="Nguyen Van B" age="27">
                Is Description -> props.children
            </Person>
            <Person fullname="Nguyen Van C" age="26" />
            </div>
        );
    }    
```
```
    class Person extends React.Component {
        render() {
            return (
                <div className="person">
                    <h1>Full name: {this.props.fullname}</h1>
                    <p>Age: {this.props.age}</p> 
                    <p>Description: {this.props.children}</p> -> Get props children
                </div>
            );
        }
    }
```
