<script>
import axios from 'axios'

let API_URL = `https://rickandmortyapi.com/api/character`

export default {

  data() {
    return {
      info: [],
      personajes: [],
      buscar:'',
    }
  },

  mounted() {
    axios.get(API_URL)
      .then((response) => {
        this.info = response.data.info;
        this.personajes = response.data.results;
      })
  },

  methods: {
    buscador(buscar) {
      API_URL='https://rickandmortyapi.com/api/character/?name='+buscar
      console.log(API_URL)
      axios.get(API_URL)
      .then((response) => {
        console.log(response.config)
        this.info = response.data.info;
        this.personajes = response.data.results;
      })

    },

  },

}

</script>

<template>
  <h2>Hay {{ info.count }} personajes en el programa de Rick & Morty</h2>
  <input type="text" v-model="buscar" class="border border-black">

  <button @click="buscador(buscar)" class="bg-orange-400 border border-black">enviar</button>

  <ul>
    <div>
    <li v-for="p in personajes" >
      <div class="border border-black uul" style="margin: 10px 10px 10px 10px">
        <a class="person">id:{{ p.id }}</a>
        <a class="person">{{ p.name }} </a> 
        <img v-bind:src=" p.image" alt="Rick y Morty">
      </div>
    </li>
    </div>
  </ul>
</template>

<style type="text/css">
  .uul{
    padding: 15px;
  }
  .person{
    display: block;
  }
</style>