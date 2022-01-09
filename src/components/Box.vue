<template>
   <div :style="estilo" class="box">
      <p style="color: rgb(90, 90, 90)">
         parameters: offset-x | offset-y | blur-radius | spread-radius | color
      </p>
      <br />
      <input
         id="texto"
         type="text"
         class="text"
         size="30"
         spellcheck="false"
         ref="texto"
         readonly="readonly"
         v-bind:value="builded"
      />
      <button @click="copiarClipboard">Copy to clipboard</button>
   </div>
</template>

<script>
   export default {
      props: {
         xoff: Number,
         yoff: Number,
         blurr: Number,
         sprr: Number,
         cor: String
      },
      computed: {
         estilo() {
            return {
               boxShadow: `${this.xoff}px ${this.yoff}px ${this.blurr}px ${this.sprr}px ${this.cor}`,
            };
         },
         builded() {
            return `boxShadow: ${this.xoff}px ${this.yoff}px ${this.blurr}px ${this.sprr}px ${this.cor};`
         }

      },
      methods: {
         copiarClipboard() {
            document.execCommand('copy');
            this.$refs.texto.select()

         }
      }

   }
</script>

<style scoped>
   .box {
      border: 1px solid black;
      width: 300px;
      height: 150px;
      margin: 40px;
      text-align: center;
      padding: 10px;
   }
   .box button {
      padding: 10px;
      margin: 10px;
   }
</style>
