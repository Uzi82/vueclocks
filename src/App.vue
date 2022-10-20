<template>
  <div class="fullscreen">
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
      time: []
    }
  },
  mounted(){
    setInterval(()=>{
      this.time = [moment().format('HH'), moment().format('mm'), moment().format('ss')]
    }, 1000)
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
</style>