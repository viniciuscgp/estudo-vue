<template>
   <div :style="estilo" class="box">
      <p>{{ estilo }}</p>
   </div>
</template>

<script>
   export default {
      props: [
         'xoff',
         'yoff',
         'cor'
      ],
      computed: {
         estilo() {
            return {
               boxShadow: `${this.xoff}px ${this.yoff}px ${this.cor}`,
            };
         }
      },
      mounted() {
         alert(this.cor)
      }

   }
</script>

<style scoped>
   .box {
      border: 1px solid black;
      width: 200px;
      height: 200px;
      margin: 20px;
   }
</style>
