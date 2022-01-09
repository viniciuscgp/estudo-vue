<template>
   <div class="painel">
      <header>
         <p>Controller</p>
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
            xoff: 5,
            yoff: 5,
            cor: "#FF4040"
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
         notifica() {
            this.$emit("onMudouAlgumValor", {
               xoff: this.xoff,
               yoff: this.yoff,
               cor: this.cor
            })
         }

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