<template>
   <div id="app" class="container b">
      <Box :xoff="25" :yoff="25" :cor="blue"></Box>
   </div>
</template>

<script>
   import Box from '@/components/Box.vue'

   export default {
      name: 'App',
      components: {
         Box
      },
   }
</script>

<style>
   * {
      box-sizing: border-box;
      margin: 0px;
      padding: 0px;
   }
   #app {
      width: 100vw;
      height: 100vh;
   }

   .b {
      border: 15px solid blueviolet;
   }

   .container {
      display: flex;
      justify-content: space-around;
      align-items: center;
   }
</style>
