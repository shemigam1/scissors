<template>
    <div class="w-screen overflow-x-hidden">
        <Navbar />
        <div class="flex flex-col mt-5 justify-center">
            <section class="w-[90%] md:w-[60%] flex flex-col items-center justify-center gap-5 mx-auto">
                <p class="text-pretty md:text-center text-5xl font-bold">Optimixe your Online Experience With
                    Our Advanced
                    URL
                    Shortening
                    Solution</p>
                <p class="text-pretty md:text-center">Personalize your shortened URLs to align with your
                    brand identity.
                    Utilize custom slugs, branded
                    links, and domain customization options to reinforce your brand presence and enhance user
                    engagement.</p>
                <div class="">
                    <a href="">Sign Up</a>
                    <a href="">Learn More</a>
                </div>

            </section>

            <section class="mt-5 w-[90%] justify-evenly items-center md:flex-row flex flex-col gap-5 mx-auto">
                <p class=" text-2xl text-left">One Stop. Four Possibilities</p>
                <ul class="flex flex-col md:flex-row gap-10">
                    <li class="flex md:flex-col gap-4"><span class=" text-xl">3M</span><span>Active Users</span></li>
                    <li class="flex md:flex-col gap-4"><span class=" text-xl">60M</span><span>Links & QR<br>codes
                            created</span>
                    </li>
                    <li class="flex md:flex-col gap-4"><span class=" text-xl">1B</span><span>Clicked &
                            Scanned<br>connections</span></li>
                    <li class="flex md:flex-col gap-4"><span class=" text-xl">300k</span><span>App Integrations</span>
                    </li>
                </ul>
            </section>

            <section class="flex justify-center items-center mt-6 h-60 bg-black w-screen">
                <div
                    class="md:w-[40%] flex justify-center items-center w-[80%] h-[60%] text-black flex-col gap-5 bg-white">
                    <input class="border border-black w-[85%]" type="text">
                    <button>Trim Url</button>
                </div>
            </section>
        </div>
    </div>
</template>

<script setup lang="ts">
import Navbar from '../components/Navbar.vue'

</script>
