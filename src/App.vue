<template>
  <!-- <header>
    <nav>
      <RouterLink to="/">Home</RouterLink>
      <RouterLink to="/signup">Signup</RouterLink>
    </nav>
  </header>
  <RouterView /> -->
  <!-- <Login /> -->
  <!-- <Signup /> -->
  <!-- <Home /> -->
  <!-- <Pricing /> -->
  <!-- <Faqs /> -->
  <router-view />
</template>

<script setup lang="ts">
import { router-view} from 'vue-router'
import Login from './views/Login.vue';
import Signup from './views/Signup.vue'
import Home from './views/Home.vue'
import Pricing from './views/Pricing.vue'
import Faqs from './views/Faqs.vue'
// import { RouterLink, RouterView } from 'vue-router';
</script>