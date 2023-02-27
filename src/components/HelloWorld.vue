<script setup>
defineProps({
  msg: {
    type: String,
    required: true,
  },
});
</script>

<template>
  <div class="greetings text-center">
    <h1 class="green text-rose-900 font-bold">{{ msg }}</h1>
    
  </div>
</template>

<style scoped>
h1 {
  font-weight: 500;
  font-size: 3rem;
  top: -10px;
  font-style: italic;

}
.green{
  text-align: center;
}
h3 {
  font-size: 1.2rem;
}

.greetings h1,
.greetings h3 {
  text-align: center;
}

@media (min-width: 1024px) {
  .greetings h1,
  .greetings h3 {
    text-align: left;
  }
}
</style>
