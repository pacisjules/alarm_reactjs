# Alarm react js system
The best overall security system : Vivint. Best overall. Vivint security

## Sample image
### First View
Here before you set the alarm.
![image](https://user-images.githubusercontent.com/51479761/177225885-4cafff79-c7f0-4b28-9d31-c8a950c62d13.png)

### Second View
By setting alarm then waiting the time.
![image](https://user-images.githubusercontent.com/51479761/177225978-e90c55d0-c131-4d99-b77e-ccffd5583360.png)


### Last View
Alarm arleady started.
![image](https://user-images.githubusercontent.com/51479761/177226027-643db7c8-0b97-4da1-bcbe-f5bb6e255124.png)






### Sample Codes

``` javascript
import React, { Component } from "react";
import './App.css';
import { FiClock } from 'react-icons/fi';



const umuziki = new Audio();
umuziki.src = "https://node-18.zeno.fm/3ncz6h98qrhvv?zs=kUq6enZQRI6vWUznFf7iOA&rj-tok=AAABgU63ytEAYqDDS9Hnk8GTjQ&rj-ttl=5";

class App extends Component {

  state = {
    number: 1,
    period: "..",
    message: "Time now playing Kiss FM Rwanda stream....",
    show: "",
    setH: "24",
    setM: "00",
    setS: "0",
    setted: 1,
    txtDis: "",
    me: "SET ALARM",
    btncolor: "#000224",
    play: 0,
  }


  play = () => {

    if (this.state.play === 1) {
      umuziki.play();
      this.setState({
        play: 0,
      })
    }
  }


  stop = () => {
    umuziki.pause();
    this.setState({
      play: 0,
      show: "",
    })
  }



  componentDidMount() {

    setInterval(() => {
      var date = new Date();
      var hour = date.getHours();
      var fullclock = date.getHours() + ":" + date.getMinutes() + ":" + date.getSeconds();
      var timeSetted = this.state.setH + ":" + this.state.setM + ":" + this.state.setS;



      this.setState({
        number: date.getHours() + ":" + date.getMinutes() + ":" + date.getSeconds()
      })

      if (hour >= 0 && hour <= 12) {
        this.setState({
          period: "AM"
        })
      } else {
        this.setState({
          period: "PM"
        })
      }

      if (fullclock === timeSetted && this.state.setted === 1) {
        umuziki.play();
        this.setState({
          show: this.state.message,
          setted: 0,
          txtDis: "",
          btncolor: "#000224",
          me: "SET ALARM",
          setH: "24",
          setM: "00",
          setS: "0",
          play: 1,
        })
      }
    }, 500)
  }

  render() {
    return (
      <>
        <div className="container">

          <div className="akazu">
            <p className="clock"><FiClock style={{
              color: "#e534eb",
              fontSize: "30px",
              marginRight: "10px",
              animation: "isaha 5s infinite"
            }} />{this.state.number} {this.state.period}</p><br />



            <div className="messeger">
              <h3>Set alarm (Kiss FM Rwanda stream)</h3>
              <br />
              <div className="ibihe">
                <input type={"number"} min={"0"} max={"23"} value={this.state.setH} onChange={(e) => {
                  this.setState({
                    setH: e.target.value
                  })
                }} disabled={this.state.txtDis} />:

                <input type={"number"} min={"0"} max={"23"} value={this.state.setM} onChange={(e) => {
                  this.setState({
                    setM: e.target.value
                  })
                }} disabled={this.state.txtDis} />:

                <input type={"number"} min={"0"} max={"23"} value={this.state.setS} onChange={(e) => {
                  this.setState({
                    setS: e.target.value
                  })
                }} disabled={this.state.txtDis} />
              </div>

              <br />

              <button onClick={() => {
                umuziki.pause();
                this.setState({
                  setted: 1,
                  txtDis: "disabled",
                  me: "ALARM SETTED",
                  btncolor: "#78004c"
                })
              }}
                style={{
                  backgroundColor: this.state.btncolor,
                }}
              >{this.state.me}</button>
              <br />
              <button onClick={this.stop} style={{
                display: this.state.play === 1 ? "block" : "none",
              }}>STOP RADIO</button>
              <p>{this.state.info}</p>
              <p>{this.state.show}</p>
              <br />
              <br />
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



