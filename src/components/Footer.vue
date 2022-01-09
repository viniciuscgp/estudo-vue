<template>
   <div class="footer row">
      <a href="https://twitter.com/viniciuscgp">
         <div class="row">
            <span>Me siga no </span>
            <img width="16" height="16" src="@/assets/twiterlogo.png" alt="" />
         </div>
      </a>
   </div>
</template>

<script>
   export default {

   }
</script>

<style scoped>
   .footer {
      text-align: center;
      height: 40px;
      width: 100%;
      position: fixed;
      bottom: 0px;
      background-color: #404040;
      color: white;
      font-size: small;
   }
   .footer .row {
      display: flex;
      flex-direction: row;
      justify-content: center;
      align-items: center;
   }
   .footer a {
      text-decoration: none;
      color: yellow;
   }
   .footer a:link a:visited {
      color: white;
   }
   .footer a:hover {
      color: white;
   }
   .footer img {
      margin: 10px;
   }
</style>