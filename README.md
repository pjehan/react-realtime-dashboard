# ReactJS realtime dashboard
Display a dashboard and animate widgets when value change.

## How to use

### Dashboard

Props:
- col (int): Number of columns
- row (int): Number of rows
- gutter (int): Gutter size (in px)
- animationClassIn (string): Class to add to every widgets when animation start
- animationClassOut (string): Class to add to every widgets when animation end

### Widget

Props:
- size (string): Widget size. Can be 'normal', 'large', 'tall' or 'big'
- animationClassIn (string): Class to add when animation start
- animationClassOut (string): Class to add when animation end

Update the component value with animation:
```js
componentDidMount() {
  this.timer = setInterval(() => {
    this.props.animate().then(() => this.setState({date: new Date()}))
  }, 3000);
}
```

### Example

```jsx
import React, { Component } from 'react';
import { Dashboard, Widget } from 'react-realtime-dashboard';
import animatecss from 'animate.css';

class App extends Component {
  render() {
    return (
      <Dashboard row={4} col={3} gutter={10} animationClassIn='animated flipInX' animationClassOut='animated flipOutX'>
        <Widget size='large'>
          <MyCustomWidget/>
        </Widget>
        <Widget>
          <AnotherCustomWidget/>
        </Widget>
      </Dashboard>
    );
  }
}
```