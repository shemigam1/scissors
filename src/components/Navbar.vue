<template>
    <header class="">
        <nav class="md:flex justify-between shadow items-center md:w-[90%] w-screen mx-auto py-6">
            <div class="">
                <img class="w-[40%] md:[w-70%]" src="../assets/Logo.svg" alt="">
            </div>
            <span>
                <img :src="[open ? '../assets/hamburger.svg' : '../assets/close.svg']" src="../assets/"
                    class="cursor-pointer absolute md:hidden right-6 top-1.5 " onclick="" alt="">
            </span>
            <ul class="md:flex md:items-center md:px-0 px-10 md:pb-0 pb-10 md:static absolute md:w-auto w-full top-14 duration-700 ease-in"
                :class="[open ? 'left-0' : 'left-[-100%]']">
                <li class="md:mx-4 md:my-0 my-6">My URLs</li>
                <li class="md:mx-4 md:my-0 my-6">Features</li>
                <li class="md:mx-4 md:my-0 my-6">Pricing</li>
                <li class="md:mx-4 md:my-0 my-6">Analytics</li>
                <li class="md:mx-4 md:my-0 my-6">FAQs</li>
                <p>Log in</p>
                <a href="">Try for free</a>
            </ul>
            <!-- <div class="">
            </div> -->
        </nav>
    </header>
</template>

<script setup lang="ts">
import { ref } from 'vue'
let open = ref(false)
const toggleMenu = () => { }

</script>