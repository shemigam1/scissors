<template>
    <!-- bg-[#50514f] -->
    <header class=" bg-[#50514f]">
        <nav class="flex justify-between items-center md:w-[90%] w-screen mx-auto py-2 px-6">
            <div class="">
                <!-- <img class="" src="../assets/Logo.svg" alt=""> -->
                <RouterLink to="/" class="text-3xl text-[#b4adea] font-semibold">SlimCase</RouterLink>
            </div>
            <span @click="toggleMenu()" class="md:hidden">
                <img src="../assets/hamburger.svg" onclick="" :class="[open ? 'hidden' : 'inline-block']" alt="">
                <img src="../assets/close.svg" onclick="" :class="[open ? 'inline-block' : 'hidden']" alt="">
            </span>

            <ul class=" md:flex md:items-center md:px-0 px-10 md:pb-0 pb-10 md:static absolute md:w-auto w-full top-14 duration-700 ease-in bg-[#50514f] md:bg-none my-6 mr-6"
                :class="[open ? 'left-0' : 'left-[-100%]']">
                <li class="md:mx-4 md:my-0 my-6 hover:text-[#b4adea]">
                    <RouterLink to="/dashboard">My URLs</RouterLink>
                </li>
                <!-- <li class="md:mx-4 md:my-0 my-6 hover:text-[#b4adea]">
                    <RouterLink to="/">Features</RouterLink>
                </li> -->
                <li class="md:mx-4 md:my-0 my-6 hover:text-[#b4adea]">
                    <RouterLink to="/pricing">Pricing</RouterLink>
                </li>
                <!-- <li class="md:mx-4 md:my-0 my-6">Analytics</li> -->
                <li class="md:mx-4 md:my-0 my-6 hover:text-[#b4adea]">
                    <RouterLink to="/faqs">FAQs</RouterLink>
                </li>
                <div class=" flex gap-4 justify-center items-center">
                    <p @click="handleLogin" class="hover:text-[#b4adea] hover:cursor-pointer">Log in</p>
                    <p class="bg-[#b4adea] hover:text-[#b4adea] hover:bg-[#50514f] hover:cursor-pointer text-xl font-semibold px-4 py-2 rounded-2xl"
                        @click="handleSignup">Try for
                        free
                    </p>
                </div>
            </ul>
            <!-- <div class="">
            </div> -->
        </nav>
    </header>
</template>

<script setup lang="ts">
import { RouterLink } from 'vue-router'
import { useRouter } from 'vue-router';
import { ref } from 'vue'

const isLoggedIn = ref(false)
const router = useRouter();

let open = ref(false)
const toggleMenu = () => {
    open.value = !open.value
}

const handleSignup = () => {
    router.push('/signup')
};
const handleLogin = () => {
    router.push('/login')
};

router.beforeEach((to, from, next) => {
    open.value = false;
    next();
})

</script>