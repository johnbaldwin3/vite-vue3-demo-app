<script setup lang="ts">
import HelloWorld from './components/HelloWorld.vue';
// This starter template is using Vue 3 <script setup> SFCs
// Check out https://v3.vuejs.org/api/sfc-script-setup.html#sfc-script-setup
</script>

<template>
  <div class="definitive-statement"><img alt="Vue logo" src="./assets/logo.png" /><h1> > </h1> <img alt="Angular logo" src="./assets/ang.png" /></div>
  <h6>just kidding..... maybe</h6>
  <HelloWorld msg="Hello Vue 3 + TypeScript + Vite" />
  <div class="notifications-container"></div>
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.definitive-statement {
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: center;
}
</style>
