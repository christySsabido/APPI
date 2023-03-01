<script setup>
import { RouterLink, RouterView } from "vue-router";
import HelloWorld from "./components/HelloWorld.vue";
</script>

<template>
  <header class="base bg-center ">
    

    <div class="wrapper">
      <HelloWorld msg="Personajes de Rick & Morty" />

      <nav class="opcion font-bold">
        <RouterLink to="/"><a class="inicio text-2xl ">Inicio</a></RouterLink>
        <RouterLink to="/personajes"><a class="inicio text-2xl">Personajes</a></RouterLink>
        <RouterLink to="/about"><a class="inicio text-2xl">Acerca de</a></RouterLink>
      </nav>
    </div>

    
  </header>

  <RouterView />
</template>

<style scoped>
header {
  line-height: 1.5;
  max-height: 100vh;
}
.opcion{
  margin: 180px 220px 0px 170px;

}

.inicio{
  text-shadow: 2px 5px 2px darkcyan;
}
.base{
  background-image: url(https://www.xtrafondos.com/descargar.php?id=9235&resolucion=3840x2160); 
  background-size: cover;
  margin-bottom: 500 px;

}
.wrapper{
  margin: 10px 10px 10px 450px;

}
.logo {
  display: block;
  margin: 0 auto 2rem;
}

nav {
  width: 100%;
  font-size: 12px;
  text-align: center;
  margin-top: 2rem;
}

nav a.router-link-exact-active {
  color: var(--color-text);
}

nav a.router-link-exact-active:hover {
  background-color: transparent;
}

nav a {
  display: inline-block;
  padding: 0 1rem;
  border-left: 1px solid var(--color-border);
}

nav a:first-of-type {
  border: 0;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }

  nav {
    text-align: left;
    margin-left: -1rem;
    font-size: 1rem;

    padding: 1rem 0;
    margin-top: 1rem;
  }
}
</style>
