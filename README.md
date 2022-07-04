# Alarm react js system
The best overall security system : Vivint. Best overall. Vivint security

### Sample image
![LightMode](https://user-images.githubusercontent.com/51479761/177199841-3e23efd5-6b41-456e-83bf-2ecdb3ffab7b.PNG)

### Sample Codes
``` javascript
import React from "react";
import "./App.css";
import Mainstream from "./components/Mainstream.jsx";

export default class App extends React.Component {
  state = {
    bgcolor: "#696969",
    switchs: true,
    anime:"",
    ctcolor: "#cbd4d9",
    ctborderrd:"20px",
    message:"OFF",
    photoimg: "grayscale(0%)",
  };

  render() {
    return (
      <div className="App">
        <Mainstream/>
      </div>
    );
  }
}
```


