<template>
   <div id="app">
      <header class="header">
         <h1>Y A S B</h1>
         <h3>Yet Another Shadow Builder</h3>
      </header>
      <div style="width: 100%; height: 100%" class="container-coluna">
         <Painel @onMudouAlgumValor="mudouAlgumValor" />
         <Box
            :inset="inset"
            :xoff="xoff"
            :yoff="yoff"
            :blurr="blurr"
            :sprr="sprr"
            :cor="cor"
         >
         </Box>
      </div>
      <Footer />
   </div>
</template>

<script>
   import Box from './components/Box.vue'
   import Painel from './components/Painel.vue'
   import Footer from './components/Footer.vue'

   export default {
      name: 'App',
      components: {
         Box,
         Painel,
         Footer
      },
      methods: {
         mudouAlgumValor(dados) {
            this.inset = dados.inset;
            this.xoff = dados.xoff;
            this.yoff = dados.yoff;
            this.blurr = dados.blurr;
            this.sprr = dados.sprr;
            this.cor = dados.cor;
         }
      },
      data() {
         return {
            inset: false,
            xoff: 1,
            yoff: 1,
            blurr: 1,
            sprr: 1,
            cor: "#000000"
         }
      }
   }
</script>

<style>
   * {
      box-sizing: border-box;
      margin: 0px;
      padding: 0px;
      font-family: "Roboto Condensed", sans-serif;
   }

   body {
      background-color: rgb(69, 127, 150);
   }

   #app {
      width: 100vw;
      height: 100vh;
      text-align: center;
   }

   .b {
      border: 0px solid blueviolet;
   }

   .container-coluna {
      display: flex;
      flex-direction: column;
      justify-content: flex-start;
      align-items: center;
   }
   .header {
      padding: 20px;
      margin: 0px 0px 30px 0px;
      background-color: #303030;
      color: white;
   }
</style>
