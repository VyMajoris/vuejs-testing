<template>
  <div>

    <img id="qrcode"></img>
    <div class="input-field">
      <input v-model="QRcodeText" 
      placeholder="Escreva alguma coisa e de Ok para adicionar à lista" 
      id="first_name" type="text" class="validate">
      <a @click="$emit('qrCodeOK', QRcodeText )" class="waves-effect waves-light btn">OK</a>
    </div>



  </div>
</template>

<script>
import QRious from 'qrious'

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
          size: 200,
          value: val,
        })
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