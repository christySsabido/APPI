<script setup>
import WelcomeItem from "./WelcomeItem.vue";
import DocumentationIcon from "./icons/IconDocumentation.vue";
import ToolingIcon from "./icons/IconTooling.vue";
import EcosystemIcon from "./icons/IconEcosystem.vue";
import CommunityIcon from "./icons/IconCommunity.vue";
import SupportIcon from "./icons/IconSupport.vue";
</script>

<template>
  <WelcomeItem>
    <template >
      <DocumentationIcon />
    </template>
    <template >Rick y Morty</template>

    <p href="https://vuejs.org/" target="_blank" rel="noopener" class="sino text-6xl text-center font-mono font-bold italic">Sinopsis Rick and Morty</p>

    <br>
    <br>

    <p href="https://vuejs.org/" target="_blank" rel="noopener" class="texto text-xl font-sans font-medium">Rick Sánchez es la definición exacta de "científico loco". Es alcohólico, es un genio, es irresponsable y está loco. Rick acaba de mudarse a casa de su hija Beth y allí recuerda que tiene un nieto llamado Morty. Sin preguntar a nadie, decide que va a obligarle a que le acompañe a todo tipo de aventuras para que el chico se vuelva inteligente como él y no se convierta en un idiota como Jerry, padre de Morty y yerno de Rick.

      <br>
      <br>

      Así, Rick y Morty comienzan a vivir aventuras intergalácticas a pesar de que la familia no quiere que lo sigan haciendo. Poco a poco tienen que intentar encontrar un equilibrio entre su vida familiar y sus viajes a través del espacio y por distintas realidades paralelas, algo que no es fácil para el pequeño Morty que es incapaz de tener una vida normal al margen de su abuelo.</p>
    </WelcomeItem>

</template>
<style scoped>
  .texto{
    margin: 5px 100px 50px 100px;
    text-align: justify;
  }

  .sino{
    margin: 40px 0px 0px 0px;
  }
</style>


