# Getting Started

Let's start with some code. As you can see, Inferno intentionally keeps the same, good, design ideas as React regarding components: one-way data flow and separation of concerns.

In these examples, JSX is used via the [Inferno JSX Babel Plugin](https://github.com/infernojs/babel-plugin-inferno) to provide a simple way to express Inferno virtual DOM. You do not need to use JSX, it's completely **optional**, you can use [hyperscript](https://github.com/trueadm/inferno/tree/master/packages/inferno-hyperscript) or [createElement](https://github.com/trueadm/inferno/tree/master/packages/inferno-create-element) (like React does).

```jsx
import Inferno from 'inferno';

const message = "Hello world";

Inferno.render(
  <MyComponent message={ message } />,
  document.getElementById("app")
)
```
Furthermore, Inferno also uses ES6 components like React:

```jsx
import Inferno from 'inferno';
import Component from 'inferno-component';

class MyComponent extends Component {
  constructor(props) {
    super(props);
    this.state = {
      counter: 0
    }
  }
  render() {
    return (
      <div>
        <h1>Header!</h1>
        <span>Counter is at: { this.state.counter }</span>
      </div>
    )
  }
}

Inferno.render(<MyComponent />, document.getElementById('app'));
```

### More Examples

- [**Simple Clock** (@JSFiddle)](https://jsfiddle.net/o01mvsyn/)
