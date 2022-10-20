<template>
  <div>
    {{time[0]}}:{{time[1]}}:{{time[2]}}
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