<template>
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
import setLight from '/vueclocks/public/particlesJS/particles.js'
import moment from 'moment'
export default {
  data(){
    return{
      time: []
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
        document.getElementsByClassName('particles-vue')[0].style="background-color: #FFFFFF";
        setLight();
      }
      if(theme == 1){
      }
      if(theme == 2){
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
  .theme__image{
    width: 2.5rem;
    height: 2.5rem;
    margin-left: auto;
    margin-right: auto;
}
</style>