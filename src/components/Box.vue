<template>
   <div :style="estilo" class="box">
      <p>Xoff:{{ xoff }}</p>
      <p>Yoff:{{ yoff }}</p>
      <p>Cor:{{ cor }}</p>
   </div>
</template>

<script>
   export default {
      props: ['xoff', 'yoff', 'cor'],
      computed: {
         estilo() {
            return {
               boxShadow: `${this.xoff}px ${this.yoff}px ${this.cor}`,
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
      width: 100px;
      height: 100px;
      margin: 40px;
      text-align: center;
      padding: 10px;
   }
</style>
