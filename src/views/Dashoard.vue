<template>
    <DashNav />
    <div>
        <section class="flex justify-center items-center py-4 bg-[#b4adea]">
            <Shortener />
        </section>

        <section>

        </section>
    </div>
</template>

<script setup lang="ts">
import DashNav from '../components/DashNav.vue';
import Shortener from '../components/Shortener.vue';
import { database } from '../utils/firebase';
import { toast } from 'vue3-toastify'
import QRCodeVue3 from 'qrcode-vue3';
import { useRouter } from 'vue-router'
import { ref, set, serverTimestamp, push, get, getDatabase } from 'firebase/database'

const router = useRouter();
let linkCollectionsRef = ref(database, 'linkCollections')
//   // Retrieve stored shortened link when the component is created
const storedShortenedLink = localStorage.getItem('shortenedLink');
if (storedShortenedLink) {
    let shortenedLink = storedShortenedLink;
}

</script>

<style scoped></style>