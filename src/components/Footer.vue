<template>
   <div class="footer">
      <a href="https://twitter.com/viniciuscgp">
         <span>Me siga no </span>
      </a>
      <img width="16" height="16" src="@/assets/twiterlogo.png" alt="" />
   </div>
</template>

<script>
   export default {

   }
</script>

<style>
   .footer {
      display: flex;
      flex-direction: row;
      justify-content: center;
      align-items: center;
      text-align: center;
      height: 40px;
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
   .footer img {
      margin: 10px;
   }
</style>