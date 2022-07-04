# Alarm react js system
The best overall security system : Vivint. Best overall. Vivint security

### Sample image
![cv](https://user-images.githubusercontent.com/51479761/177211030-ca0d08ca-605f-4015-8fd9-970fbb0fb171.PNG)


### Sample Codes

``` javascript
import React, { Component } from "react";
import './App.css';


class App extends Component {

  state={
    number:1,
    period:"..",
    message:"",
    show:"",
    set:"21:40:0"
  }


  componentDidMount(){
    
    setInterval(()=>{
      var date=new Date();
      var hour=date.getHours();
      var fullclock=date.getHours()+":"+date.getMinutes()+":"+date.getSeconds();
      
      this.setState({
        number:date.getHours()+":"+date.getMinutes()+":"+date.getSeconds()
      })

      if(hour>=0&&hour<=12){
        this.setState({
          period:"AM"
        })
      }else{
        this.setState({
          period:"PM"
        })
      }

      if (fullclock === this.state.set) {
        this.setState({
          show: this.state.message
        })
      }

    },500)
  }

  render() {
    return (
      <>
        <div className="container">
          <div className="akazu">
            <p className="clock">{this.state.number} {this.state.period}</p><br/>
            <div className="messeger">
              <input type={"text"} placeholder="Type a message" value={this.state.set} onChange={(e)=>{
                this.setState({
                  set:e.target.value
                })
              }}/><br/>
              <input type={"text"} value={this.state.message} placeholder="Type a message"onChange={(e)=>{
                this.setState({
                  message:e.target.value
                })
              }}/><br/>
              <br/>
              <br/>
              <p>{this.state.show}</p>
            </div>
          </div>
        </div>
      </>
    );
  }
}

export default App;


```

### Sample link
Link is here https://papaya-truffle-e08667.netlify.app



