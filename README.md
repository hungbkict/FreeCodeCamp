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

```
const List = (props) => {
  { /* Change code below this line */ }
  return <p>{props.tasks.join(", ")}</p>
  { /* Change code above this line */ }
};

class ToDo extends React.Component {
  constructor(props) {
    super(props);
  }
  render() {
    return (
      <div>
        <h1>To Do Lists</h1>
        <h2>Today</h2>
        { /* Change code below this line */ }
        <List tasks={["Eat","Sleep"]}/>
        <h2>Tomorrow</h2>
        <List tasks={["Fck","ML", "DN"]}/>
        { /* Change code above this line */ }
      </div>
    );
  }
};
```

# 15. Use Default Props

```
const ShoppingCart = (props) => {
  return (
    <div>
      <h1>Shopping Cart Component</h1>
    </div>
  )
};
// Change code below this line

ShoppingCart.defaultProps = { items : 0};
```

# 16. Override Default Props

```
const Items = (props) => {
  return <h1>Current Quantity of Items in Cart: {props.quantity}</h1>
}

Items.defaultProps = {
  quantity: 0
}

class ShoppingCart extends React.Component {
  constructor(props) {
    super(props);
  }
  render() {
    { /* Change code below this line */ }
    return <Items  quantity={10}/>
    { /* Change code above this line */ }
  }
};
```

# 17. Use PropTypes to Define the Props You Expect

```
const Items = (props) => {
  return <h1>Current Quantity of Items in Cart: {props.quantity}</h1>
};

Items.propTypes = { quantity: PropTypes.number.isRequired };

Items.defaultProps = {
  quantity: 0
};


class ShoppingCart extends React.Component {
  constructor(props) {
    super(props);
  }
  render() {
    return <Items />
  }
};
```

# 18. Access Props Using this.props

```
class App extends React.Component {
  constructor(props) {
    super(props);

  }
  render() {
    return (
        <div>
            { /* Change code below this line */ }
            <Welcome name={"Hung"}/>
            { /* Change code above this line */ }
        </div>
    );
  }
};

class Welcome extends React.Component {
  constructor(props) {
    super(props);

  }
  render() {
    return (
        <div>
          { /* Change code below this line */ }
          <p>Hello, <strong>{this.props.name}</strong>!</p>
          { /* Change code above this line */ }
        </div>
    );
  }
};
```

#19. Review Using Props with Stateless Functional Components

```
class CampSite extends React.Component {
  constructor(props) {
    super(props);
  }
  render() {
    return (
      <div>
        <Camper/>
      </div>
    );
  }
};

const Camper = (props)=>{
  return <p>{props.name}</p>
}

Camper.propTypes = { name: PropTypes.string.isRequired };

Camper.defaultProps = {
  name: 'CamperBot'
};
```

# 20. Create a Stateful Component

```
class StatefulComponent extends React.Component {
  constructor(props) {
    super(props);
    // Only change code below this line
    this.state = {
      name: "Hung"
}
    // Only change code above this line
  }
  render() {
    return (
      <div>
        <h1>{this.state.name}</h1>
      </div>
    );
  }
};
```

# 21. Render State in the User Interface

```
class MyComponent extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      name: 'freeCodeCamp'
    }
  }
  render() {
    return (
      <div>
        { /* Change code below this line */ }
          <h1>{this.state.name}</h1>
        { /* Change code above this line */ }
      </div>
    );
  }
};
```

#22. Render State in the User Interface Another Way

```
class MyComponent extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      name: 'freeCodeCamp'
    }
  }
  render() {
    // Change code below this line
    const name = this.state.name;

    // Change code above this line
    return (
      <div>
        { /* Change code below this line */ }
          <h1>{name}</h1>
        { /* Change code above this line */ }
      </div>
    );
  }
};
```

#23. Set State with this.setState

```
class MyComponent extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      name: 'Initial State'
    };
    this.handleClick = this.handleClick.bind(this);
  }
  handleClick() {
    // Change code below this line
    this.setState(
      {
        name: "React Rocks!"
      }
    );
    // Change code above this line
  }
  render() {
    return (
      <div>
        <button onClick={this.handleClick}>Click Me</button>
        <h1>{this.state.name}</h1>
      </div>
    );
  }
};
```