<script>
  import KapufQuiz from './components/KapufQuiz.vue'
  export default {
    components: {
      'kapufQuiz': KapufQuiz
    }
  }
</script>
<template>
  <kapuf-quiz/>
</template>

<style>
@import './assets/base.css';
    body {
        background-image:url(./assets/background.png);
        background-repeat: no-repeat;
        background-position: center;
    }
</style>
