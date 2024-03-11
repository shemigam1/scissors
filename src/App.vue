<template>
  <!-- <header>
    <nav>
      <RouterLink to="/">Home</RouterLink>
      <RouterLink to="/signup">Signup</RouterLink>
    </nav>
  </header>
  <RouterView /> -->
  <!-- <Login /> -->
  <Signup />
</template>

<script setup lang="ts">
import Login from './views/Login.vue';
import Signup from './views/Signup.vue'
// import { RouterLink, RouterView } from 'vue-router';
</script>