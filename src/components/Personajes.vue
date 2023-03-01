<script>
import axios from 'axios'

let API_URL = `https://rickandmortyapi.com/api/character`

export default {

  data() {
    return {
      info: [],
      personajes: [],
      buscar:'',
      pagina:1,
      anterior:null,
      siguiente:null,
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
      axios.get(API_URL)
      .then((response) => {
        console.log(response.config)
        this.info = response.data.info;
        this.personajes = response.data.results;
      })

    },
    navpag(num){
      API_URL='https://rickandmortyapi.com/api/character/?page='+this.pagina
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
  <h2 class="text-center">Hay {{ info.count }} personajes en el programa de Rick & Morty</h2>
  <input type="text" v-model="buscar" class="border border-2 border-lime-500 w-96">

<button @click="buscador(buscar)" class="envi bg-green-500 shadow-lg shadow-green-500/50 text-white font-bold py-1 px-3 rounded border-black" >Buscar</button>
  <br>
  <br>
<button v-if="pagina!==1" @click="$event => navpag(pagina--) " class="Boton bg-cyan-500 shadow-lg shadow-cyan-500/50 text-white font-bold py-1 px-3 rounded">Anterior</button> 
<button v-if="pagina!==this.info.pages" @click="$event => navpag(pagina++)" class="bg-cyan-500 shadow-lg shadow-cyan-500/50 text-white font-bold py-1 px-3 rounded">Siguiente</button>


  <ul>
    <div class="contenedor">
    <li v-for="p in personajes" >
      <div class="border border-black uul " style="margin: 10px 10px 10px 10px">
        <img v-bind:src=" p.image" alt="Rick y Morty">
        <a class="person">Id: {{ p.id }}</a>
        <a class="person">Nombre: {{ p.name }} </a> 
        <a class="person">Especie: {{ p.species }} </a> 
        <a class="person">Estado: {{ p.status }} </a> 
        <a class="person">Género: {{ p.gender }} </a>  
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
    margin: 5px 10px 0px 80px;
    font-weight: 700;
    font-size: 24px;
  }

  .Boton{
    margin: 0px 10px 8px 600px;
  }

  .envi{
    margin: 0px 10px 8px 6px;
  }

  .contenedor{
    background-image: url(https://img.freepik.com/vector-gratis/fondo-galaxia-acuarela-creativa_79603-1388.jpg);
    background-size: cover;
    margin-bottom: 100 px;
  }
  .border{
    margin: 25px 0px 10px 500px;
  }

  h1{
    text-align: center;
    font-family: ui-monospace;
    font-size: 24px;
  }
  h2{
    font-family: ui-monospace;
    font-size: 24px;
  }
</style>