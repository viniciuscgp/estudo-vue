<template>
   <div class="footer">
      <a href="https://twitter.com/viniciuscgp">
         Vamos nos seguir no Twitter ? Clica Aqui!
      </a>
   </div>
</template>

<script>
   export default {

   }
</script>

<style>
   .footer {
      display: flex;
      flex-direction: column;
      justify-content: space-around;
      text-align: center;
      height: 30px;
      width: 100%;
      position: fixed;
      bottom: 0px;
      background-color: #404040;
      color: white;
      font-size: small;
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
</style>