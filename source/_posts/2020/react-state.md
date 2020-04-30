---
title: React and State
permalink: react-state
date: 2020-04-26 16:42:35
tags: React
categories: React
---

## React and State

### Class Component
* Define state
`this.state = {lat: null};`

* Update state
`this.setState({lat: position.coords.latitude});`
Note: state is immutable, we should **never edit the object directly**, like `this.state.lat = 1`


```jsx
import React from 'react';
import ReactDOM from 'react-dom';

class App extends React.Component {
  constructor(props){
    // a good place to define react state
    super(props);

    this.state = {lat: null};

    window.navigator.geolocation.getCurrentPosition(
      position => {
        console.log(position);
        // must use setstate to modify state
        this.setState({lat: position.coords.latitude});
      },
      err => console.log(err)
    );
  }

  // React says we have to define render
  render() {
    return <div>Latitude: {this.state.lat}</div>
  }
}

ReactDOM.render(
  <App/>,
  document.querySelector("#root")
);
```
