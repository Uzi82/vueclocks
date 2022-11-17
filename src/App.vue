<template>
  <!-- <button class="hide-button" @click="hide(true)" style="left: 5%;">H</button>
  <button class="hide-button" @click="hide(false)">H</button> -->
  <div class="fullscreen 1">
    <div class="menu">
      <!-- <div class="menu-flex">
        <button class="menu-el" @click="timerOn()">Часы</button>
        <button class="menu-el" @click="timerOn()"><div class="text">Таймер</div></button>
        <button class="menu-el"><div class="text">Секундомер</div></button>
      </div> -->
    </div>
    <!-- <iframe width="360" height="240" src="https://www.youtube.com/embed/_UqOHEPkGms?autoplay=1" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe> -->
    <div class="theme">
      <button class="theme__button" @click="Theme(0)"><img class="theme__image" src="./assets/images/themes/moon.png"></button>
      <button class="theme__button" @click="Theme(1)"><img class="theme__image" src="./assets/images/themes/sun.png"></button>
      <button class="theme__button" @click="Theme(2)"><img class="theme__image" src="./assets/images/logo.png"></button>
    </div>
    <div class="column">
      <img src="./assets/images/logo.png">
      <div class="Clocks">
        {{time[0]}}:{{time[1]}}:{{time[2]}}
      </div>
    </div>
  </div>
  <div class="fullscreen 2" style="visibility: hidden;">
    <div class="theme">
      <button class="theme__button" @click="Theme(0)"><img class="theme__image" src="./assets/images/themes/moon.png"></button>
      <button class="theme__button" @click="Theme(1)"><img class="theme__image" src="./assets/images/themes/sun.png"></button>
      <button class="theme__button" @click="Theme(2)"><img class="theme__image" src="./assets/images/logo.png"></button>
    </div>
    <div class="column">
      <img src="./assets/images/logo.png">
    </div>
  </div>
</template>
<script>
import moment, { relativeTimeRounding } from 'moment'
export default {
  data(){
    return{
      time: [],
      theme: true
    }
  },
  mounted(){
    setInterval(()=>{
      this.time = [moment().format('HH'), moment().format('mm'), moment().format('ss')]
    }, 1000)
  },
  methods: {
    Theme(theme){
      if(theme == 0){
        document.getElementsByClassName('body')[0].style="background-color: #282828";
        console.log("0");
      }
      if(theme == 1){
        document.getElementsByClassName('body')[0].style="background-color: #FFFFFF";
        console.log("1");
      }
      if(theme == 2){
        document.getElementsByClassName('body')[0].style="background-color: #213547";
        console.log("2");
      }
    },
    hide(OnOrOff){
      if(OnOrOff == true){
        document.getElementsByClassName('theme')[0].style="visibility: hidden;"
      }
      if(OnOrOff == false){
        document.getElementsByClassName('theme')[0].style="visibility: visible;"
      }
    },
    timerOn(){
      document.getElementsByClassName('1')[0].style="visibility: hidden;";
      alert('1');
    },
    init: function () { 
         const script = document.createElement("script");
         script.async = true;
         script.src = "playerjs.js";
         document.head.appendChild(script);
    },
    playerjs: function () {
         var player = new Playerjs({id:"player", file:"https://plrjs.com/sample.mp4"});
    }
  },
  init: function () { 
         const script = document.createElement("script");
         script.async = true;
         script.src = "playerjs.js";
         document.head.appendChild(script);
      },
      playerjs: function () {
         var player = new Playerjs({id:"player", file:"https://plrjs.com/sample.mp4"});
      }
   };
});
function PlayerjsAsync(){
   app.playerjs();
}
</script>
<style>
  @font-face {
    font-family: time;
    src: url(./assets/fonts/time.ttf);
  }
  @font-face {
    font-family: T-bold;
    src: url(./assets/fonts/TitilliumWeb-Bold.ttf);
  }
  *{
    padding: 0px;
    margin: 0px;
  }
  .fullscreen{
    width: 100vw;
    height: 100vh;
    display: flex;
    align-items: center;
    vertical-align: middle;
    position: absolute;
    z-index: 1000;
  }
  .column{
    display: flex;
    flex-direction: column;
    align-items: center;
    margin-left: auto;
    margin-right: auto;
  }
  .Clocks {
    color: #41B883;
    font-size: 8rem;
    font-family: time;
  }
  .theme{
    display: flex;
    flex-direction: column;
    position: absolute;
  }
  .theme__button{
    width: 3rem;
    height: 3rem;
    background-color: #282828;
    border-radius: 3%;
    border: 2px;
    border-color: #000000;
    margin: 5px;
    display: flex;
    align-items: center;
  }
  .theme__button:hover{
    cursor: pointer;
  }
  .theme__image{
    width: 2.5rem;
    height: 2.5rem;
    margin-left: auto;
    margin-right: auto;
}
.menu{
  display: flex;
  z-index: 1000;
  position: absolute;
  width: 100%;
  height: 7vh;
  align-items: center;
  justify-content: center;
}
.menu-flex{
  display: flex;
  flex-direction: column;
  position: absolute;
}
.menu-el{
  width: 3rem;
  height: 3rem;
  background-color: #282828;
  border-radius: 3%;
  border: 2px;
  border-color: #000000;
  margin: 5px;
  display: flex;
  align-items: center;
}
.text{
  margin: auto auto auto auto;
  vertical-align: middle;
}
.hide-button{
  width: 20px;
  height: 20px;
  background-color: #000000;
  z-index: 1001;
  position: static;
}
</style>