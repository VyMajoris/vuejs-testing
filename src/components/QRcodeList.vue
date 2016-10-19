<template>

  <ul style="height:60vh;overflow:auto">

    <li v-for="base64, index in ids">
      <div>
        <img style="cursor:pointer" v-bind:src="base64"></img>
      </div>
      <div>
        <button class="waves-effect waves-light btn" @click="removeElement(index)">remover</button>
      </div>
    </li>
  </ul>

</template>

<script>
import QRious from 'qrious'

var permanentIds = 0;

export default {

  data () {
    return {
      ids:  [

      ]
    }
  },
    methods:{
      addQrCodeToList(QRcodeText){
      console.log("At List", QRcodeText)

      var qr = new QRious({
        value: QRcodeText
      })

      var base64 = qr.toDataURL('image/jpeg');
      this.ids.push(base64 )

      },
      removeElement(item){
            this.ids.splice(item,1)
      }
  },


   
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  h1 {
    color: #5c4867;
  }
</style>