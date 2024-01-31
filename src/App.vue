<template>
  <div id="app-wrapper">
    <AppHeader title="Husky Registration" />
    <RouterView />
  </div>
</template>

<script setup>
import { RouterView } from "vue-router";
import AppHeader from "./components/AppHeader.vue";
</script>


<style scoped>
#app-wrapper {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  text-align: center
}

</style>
