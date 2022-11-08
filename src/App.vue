<template>
  <button class="hide-button" @click="hide(true)">H</button>
  <button class="hide-button" @click="hide(false)">H</button>
  <div class="menu">
    <div class="menu-flex">
      <div class="menu-el"><div class="text">Часы</div></div>
      <div class="menu-el"><div class="text">Таймер</div></div>
      <div class="menu-el"><div class="text">Секундомер</div></div>
    </div>
  </div>
  <div class="fullscreen">
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
</template>
<script>
import moment from 'moment'
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
    }
  }
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
  margin-left: auto;
  margin-right: auto;
  flex-direction: row;
  align-items: center;
}
.menu-el{
  margin: 10px;
  width: 10vw;
  height: 4vh;
  font-family: Arial, Helvetica, sans-serif;
  text-align: center;
  color: #41B883;
  font-size: 1.5rem;
  background-color: auto;
  border: 4px solid #41B883;
  border-radius: 5%;
  margin-top: auto;
  margin-bottom: auto;
  display: flex;
}
.text{
  margin: auto auto auto auto;
  vertical-align: middle;
}
.hide-button{
  width: 20px;
  height: 20px;
  background-color: #000000;
  position: absolute;
}
</style>