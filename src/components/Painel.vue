<template>
   <div class="painel">
      <header>
         <p>Control Panel</p>
      </header>
      <br />
      <div class="linha">
         <div class="coluna">
            <label for="">x-offset</label>
            <div>
               <input type="number" v-model="xoff" />
               <button @click="decXoff">-</button>
               <button @click="incXoff">+</button>
            </div>
         </div>

         <div class="coluna">
            <label for="">y-offset</label>
            <div>
               <input type="number" v-model="yoff" />
               <button @click="decYoff">-</button>
               <button @click="incYoff">+</button>
            </div>
         </div>
      </div>

      <div class="linha">
         <div class="coluna">
            <label for="">blur-radius</label>
            <div>
               <input type="number" v-model="blurr" />
               <button @click="decBlurr">-</button>
               <button @click="incBlurr">+</button>
            </div>
         </div>

         <div class="coluna">
            <label for="">spread-radius</label>
            <div>
               <input type="number" v-model="sprr" />
               <button @click="decSprr">-</button>
               <button @click="incSprr">+</button>
            </div>
         </div>
      </div>

      <div class="cor">
         <label for="">Shadow color: </label>
         <input @change="notifica" type="color" id="" v-model="cor" />
      </div>
   </div>
</template>

<script>
   export default {
      data() {
         return {
            xoff: 13,
            yoff: 13,
            blurr: 14,
            sprr: 0,
            cor: "#615656"
         }
      },
      methods: {
         incXoff() {
            this.xoff++;
            this.notifica();
         },
         decXoff() {
            this.xoff--;
            this.notifica();
         },
         incYoff() {
            this.yoff++;
            this.notifica();
         },
         decYoff() {
            this.yoff--;
            this.notifica();
         },
         incBlurr() {
            this.blurr++;
            this.notifica();
         },
         decBlurr() {
            this.blurr--;
            this.notifica();
         },
         incSprr() {
            this.sprr++;
            this.notifica();
         },
         decSprr() {
            this.sprr--;
            this.notifica();
         },

         notifica() {
            this.$emit("onMudouAlgumValor", {
               xoff: this.xoff,
               yoff: this.yoff,
               blurr: this.blurr,
               sprr: this.sprr,
               cor: this.cor
            })
         }

      },
      mounted() {
         this.notifica();
      }

   }
</script>

<style>
   .painel {
      display: flex;
      flex-direction: column;
      flex-wrap: wrap;
      align-content: space-around;
      background-color: #202020;
      color: white;
      text-align: center;
   }

   .painel .linha {
      display: flex;
      flex-direction: row;
      flex-wrap: wrap;
      padding: 5px;
   }

   .painel .coluna {
      display: flex;
      flex-direction: column;
      margin: 10px;
      padding: 5px;
   }

   .painel header {
      padding: 8px;
      margin: 0px;
      background-color: #404040;
   }

   .painel button {
      font-size: 2em;
      width: 40px;
   }
   .painel input {
      font-size: 2em;
      width: 60px;
   }
   .painel .cor {
      margin: 10px;
      padding: 5px;
   }
</style>