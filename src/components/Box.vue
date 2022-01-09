<template>
   <div>
      <div :style="estilo" class="box">
         <p style="color: rgb(90, 90, 90)">
            parameters: offset-x | offset-y | blur-radius | spread-radius |
            color <br /><br />
            <strong style="font-size: 1.5em"> The Box </strong>
         </p>
         <br />
      </div>

      <div class="result">
         <label for="">Result:</label>
         <input
            id="texto"
            type="text"
            class="text"
            size="33"
            spellcheck="false"
            ref="texto"
            readonly="readonly"
            v-bind:value="builded"
         />
         <button @click="copiarClipboard">Copy to clipboard</button>
      </div>
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
            return `box-shadow: ${this.xoff}px ${this.yoff}px ${this.blurr}px ${this.sprr}px ${this.cor};`
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
      background-color: burlywood;
   }
   .result {
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
   }
   .result input {
      padding: 7px;
      margin: 7px;
      font-size: 0.8em;
   }
   .result button {
      padding: 7px;
      margin: 7px;
   }
</style>
