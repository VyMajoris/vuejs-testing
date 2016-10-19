<template>
  <div id="app" class="row">
    <div class="col s6">
      <QRcode @qrCodeOK="onAddQRcode"></QRcode>
       </div>
       <div style="overflow" class="col s6">
      <QRcodeList @editQrCode="editQrCode" ref="QRcodeList"></QRcodeList>
       </div>
  </div>
</template>

<script>
import QRcode from './components/QRcode'
import QRcodeList from './components/QRcodeList'

import Vue from 'vue'



export default {
  components: {
    QRcode,
    QRcodeList
  },
  methods:{
    onAddQRcode(QRcodeText){

     this.$refs.QRcodeList.addQrCodeToList(QRcodeText);
 
   
    },
    removeFromList(index){
      console.log("remove0",index)
        this.$refs.QRcodeList.todos.splice(index, 1)
    },
    editQrCode(qr){
        let {index, base64} = qr
       

    }
  },
  
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