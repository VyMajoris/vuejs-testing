<template>

  <ul>
    
  </ul>

</template>

<script>
import QRious from 'qrious'

import Vue from 'vue'


export default {

  data () {
    return {
      qrcodes:[]
    }
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

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  h1 {
    color: #5c4867;
  }
</style>