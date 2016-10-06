<template>
  <div>

    <img id="qrcode"></img>
    <div class="input-field">
      <input v-model="QRcodeText" 
      placeholder="Escreva alguma coisa e de Ok para adicionar à lista" 
      id="first_name" type="text" class="validate">

    </div>



  </div>
</template>

<script>
import QRious from 'qrious'
import Vue from 'vue'

export default {

  data () {
    return {
      msg: 'Hello Vue!',
      QRcodeText:''
    
    }
  },
  watch: {
    'QRcodeText': function (val, oldVal) {
      new QRious({
          element: document.getElementById('qrcode'),
          value: val
        })
      //send this to parent(or to another component at the same level)
      
      this.$emit('qrcode-A', val)

      this.$parent.$emit('qrcode-B', val);
    
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