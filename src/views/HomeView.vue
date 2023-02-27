<script setup>
import TheWelcome from "../components/TheWelcome.vue";
</script>

<template>
  <main class="fondo bg-gradient-to-r from-cyan-500 via-green-500 to-green-900">
    <video width="600" height="400" loop muted autoplay controls class="vide border-4 border-black">
      <source src="../components/Rick.mp4" type="video/mp4">
    </video>
    <TheWelcome />

    
    
  </main>
</template>

<style scoped>
.vide{
  margin: 0px 10px 0px 400px; 
}
  
  

</style>
