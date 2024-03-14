<template>
    <div :if="data && data.length > 0">
        <div class="" :for="item in data" :key="item.id">
            <h3>{{ item.question }}</h3>
            <span>+</span>
        </div>
        <div class="" :if="selected === item.id">{{ item.answer }}</div>
    </div>
</template>

<script setup lang="ts">
import { ref } from 'vue'
import data from '../assets/data.ts'
const selected = ref(null)
</script>
