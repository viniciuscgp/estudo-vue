<template>
   <div :style="estilo" class="box">
      <p style="color: rgb(90, 90, 90)">
         parameters: offset-x | offset-y | blur-radius | spread-radius | color
      </p>
      <p>box-shadow: {{ xoff }} {{ yoff }} {{ blurr }} {{ sprr }} {{ cor }}</p>
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
         }
      },
      mounted() {
      }

   }
</script>

<style scoped>
   .box {
      border: 1px solid black;
      width: 200px;
      height: 100px;
      margin: 40px;
      text-align: center;
      padding: 10px;
   }
</style>
