<template>
  <TheNavBar />
  <TheElder />
  <TheFooter />
</template>


<script>
import TheFooter from './components/TheFooter.vue';
import TheNavBar from './components/TheNavBar.vue';
import TheElder from './views/TheTemplate.vue';


export default {
  name: 'App',
  components: {
   TheElder,
   TheNavBar,
   TheFooter
  }
}
</script>

<style>
body {
  background-color: #ffffff !important;
}
html {
  scroll-behavior: smooth;
  scroll-padding-top: 90px; /* altura da navbar */
}


</style>