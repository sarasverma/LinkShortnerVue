<script setup>
import { RouterView } from 'vue-router'
//theme
import 'primevue/resources/themes/lara-light-indigo/theme.css'

//core
import 'primevue/resources/primevue.min.css'
</script>
<style>
* {
  padding: 0;
  margin: 0;
}
main{
  display: grid;
  place-items: center;
  height: 100dvh;
  width: 100dvw;
  background-image: url("https://images.unsplash.com/photo-1481026469463-66327c86e544?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1816&q=80");
  background-size: cover;
}

</style>
<template>
  <RouterView />
</template>
