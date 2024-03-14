<template>
    <header class="">
        <nav class="flex justify-between shadow items-center md:w-[90%] w-screen mx-auto py-6 px-6">
            <div class="">
                <img class="" src="../assets/Logo.svg" alt="">
            </div>
            <span @click="toggleMenu()" class="md:hidden">
                <img src="../assets/hamburger.svg" onclick="" :class="[open ? 'hidden' : 'inline-block']" alt="">
                <img src="../assets/close.svg" onclick="" :class="[open ? 'inline-block' : 'hidden']" alt="">
            </span>

            <ul class="md:flex md:items-center md:px-0 px-10 md:pb-0 pb-10 md:static absolute md:w-auto w-full top-14 duration-700 ease-in"
                :class="[open ? 'left-0' : 'left-[-100%]']">
                <li class="md:mx-4 md:my-0 my-6">
                    <RouterLink to="/">My URLs</RouterLink>
                </li>
                <li class="md:mx-4 md:my-0 my-6">
                    <RouterLink to="/">Features</RouterLink>
                </li>
                <li class="md:mx-4 md:my-0 my-6">
                    <RouterLink to="/pricing">Pricing</RouterLink>
                </li>
                <!-- <li class="md:mx-4 md:my-0 my-6">Analytics</li> -->
                <li class="md:mx-4 md:my-0 my-6">
                    <RouterLink to="/faqs">FAQs</RouterLink>
                </li>
                <p>Log in</p>
                <a href="">Try for free</a>
            </ul>
            <!-- <div class="">
            </div> -->
        </nav>
    </header>
</template>

<script setup lang="ts">
import { RouterLink } from 'vue-router'
import { ref } from 'vue'
let open = ref(false)
const toggleMenu = () => {
    open.value = !open.value
}

</script>