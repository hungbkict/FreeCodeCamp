# 12. Render a Class Component to the DOM

```react
class MyComponent extends React.Component{
  constructor(props) {
    super(props);
  }
  render(){
    return (
          <div id="challenge-node">
                 <h1>My First React Component!</h1>
          </div>
    );
  }
};

ReactDOM.render(<MyComponent/>, document.getElementById("challenge-node"));
```

_Sau extends không có đóng mở ngoặc_

_Cuối class có ;_

# 13. Pass Props to a Stateless Functional Component

```
const CurrentDate = (props) => {
  return (
    <div>
      <p>The current date is: {props.date}</p>
    </div>
  );
};

class Calendar extends React.Component {
  constructor(props) {
    super(props);
  }
  render() {
    return (
      <div>
        <h3>What date is it?</h3>
        <CurrentDate date={Date()}/>
      </div>
    );
  }
};
```
# 14. Pass an Array as Props
