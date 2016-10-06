<template>
  <div id="app" class="row">
    <div class="col s6">
      <QRcode></QRcode>
       </div>
       <div class="col s6">
      <QRcodeList></QRcodeList>
       </div>
   
  
  </div>
</template>

<script>
import QRcode from './components/QRcode'
import QRcodeList from './components/QRcodeList'

import Vue from 'vue'
var bus = new Vue()
bus.$on('qrcode-A', function (id) {
 console.log(id)
})
bus.$on('qrcode-B', function (id) {
 console.log(id)
})











export default {
  components: {
    QRcode,
    QRcodeList
  },
  events:{
    'qrcode-A' : function(val){
      console.log("qrcode-A",val)
    },
    'qrcode-B' : function(val){
      console.log("qrcode-B",val)
    }
  }
}
</script>

<style>
  html {
    height: 100%;
  }
  
  body {
    display: flex;
    align-items: center;
    justify-content: center;
    height: 100%;
  }
  
  #app {
    color: #2c3e50;
    margin-top: -100px;
    max-width: 600px;
    font-family: Source Sans Pro, Helvetica, sans-serif;
    text-align: center;
  }
  
  #app a {
    color: #42b983;
    text-decoration: none;
  }
</style>