<template>
   <div class="painel">
      <header>
         <p>Control Panel</p>
      </header>
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

      <div class="linha">
         <input
            ref="inset"
            @change="notifica"
            type="checkbox"
            name=""
            id="inset"
         />
         <label for="inset">Inset</label>
      </div>

      <div class="linha cor">
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
            inset: "",
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
            this.$refs.inset.checked ? this.inset = "inset" : this.inset = ""

            this.$emit("onMudouAlgumValor", {
               inset: this.inset,
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

<style scoped>
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
      align-items: center;
      padding: 1px 5px 1px 5px;
   }

   .painel .coluna {
      display: flex;
      flex-direction: column;
      padding: 1px 5px 1px 5px;
      margin: 1px 5px 1px 5px;
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
      text-align: center;
   }
   /* Chrome, Safari, Edge, Opera */
   input::-webkit-outer-spin-button,
   input::-webkit-inner-spin-button {
      -webkit-appearance: none;
      margin: 0;
   }
   /* Firefox */
   input[type="number"] {
      -moz-appearance: textfield;
   }

   input[type="checkbox"] {
      transform: scale(1.5);
   }

   .painel .cor {
      margin: 5px;
      padding: 5px;
   }

   .painel label {
      margin: 5px;
   }

   input[type="color"] {
      padding: 0px;
      margin: 0px;
      border: none;
   }

   .b {
      border: 5px solid white !important;
   }
</style>