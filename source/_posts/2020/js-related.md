---
title: js-related
permalink: js-related
date: 2020-05-04 19:24:21
tags: Javascript
categories: Javascript
---

### Js Related
#### Disable inspect(development tools), right click
 看别人博客 想白嫖一下人家代码 发现人家博客禁用了inspect :( , Google了一下自己写了一个Demo
```html 
<body oncontextmenu="return false;">
</body>

// windows:  e.ctrlKey && e.shiftKey && e.keyCode === 'I'.charCodeAt(0)
// mac: e.altKey && e.metaKey && e.keyCode === 'I'.charCodeAt(0)
<script type="text/javascript">
  document.onkeydown = function(e) {
    if(event.keyCode === 123) {
      return false;
    }
    if((e.ctrlKey || e.altKey) && (e.shiftKey || e.metaKey) && e.keyCode === 'I'.charCodeAt(0)) {
      return false;
    }
    if((e.ctrlKey || e.altKey) && (e.shiftKey || e.metaKey) && e.keyCode === 'C'.charCodeAt(0)) {
      return false;
    }
    if((e.ctrlKey || e.altKey) && (e.shiftKey || e.metaKey) && e.keyCode === 'J'.charCodeAt(0)) {
      return false;
    }
    if((e.ctrlKey || e.altKey) && (e.shiftKey || e.metaKey) && e.keyCode === 'U'.charCodeAt(0)) {
      return false;
    }
  }
</script>
```

#### this
和java不一样， 通过java的思维 truck.driveMyTruck 只是调用了car里面的sound 结果应该是vroom。 但是js里面， 会认为this指的是truck，结果就变成
`putputput`。
```javascript
class Car {
  setDriveSound(sound) {
    this.sound = sound;
  }

  drive() {
    return this.sound;
  }
}

const car = new Car();
car.setDriveSound('vroom');

const truck = {
  sound: 'putputput',
  driveMyTruck: car.drive
}

// 1
console.log(truck.driveMyTruck);

const drive = car.drive;
// 2
console.log(drive());
```

Add the constructor to bind this， to make the logic to work
```javascript
class Car {
  constructor() {
    this.drive = this.drive.bind(this);
  }

  setDriveSound(sound) {
    this.sound = sound;
  }

  drive() {
    return this.sound;
  }
}
```

#### Axio
ways for async requests
```javascript
 async onSearchSubmit(term) {
    const response = await axios.get('https://api.unsplash.com/search/photos', {
      params: {
        query: term
      },
      headers: {
        Authorization: 'Client-ID DSoo4hrs3G1mzY1BkyycAZkBT3LXLmpzc3TOI16z3-E'
      }
    });
    console.log(response.data.results);
  }
```

```javascript
  onSearchSubmit(term) {
    axios.get('https://api.unsplash.com/search/photos', {
      params: {
        query: term
      },
      headers: {
        Authorization: 'Client-ID DSoo4hrs3G1mzY1BkyycAZkBT3LXLmpzc3TOI16z3-E'
      }
    }).then(r => console.log(r));
  }
```

```javascript
onSearchSubmit = async (term) => {
    const response = await axios.get('https://api.unsplash.com/search/photos', {
      params: {
        query: term
      },
      headers: {
        Authorization: 'Client-ID DSoo4hrs3G1mzY1BkyycAZkBT3LXLmpzc3TOI16z3-E'
      }
    });
    this.setState({images: response.data.results});
  }
```


