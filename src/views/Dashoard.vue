<template>
    <DashNav />
    <div class="">
        <section class="h-[40%] flex justify-center items-center py-4 bg-[#b4adea]">
            <Shortener />
        </section>

        <section v-if="userLinks" class="flex flex-col justify-center items-center gap-4 py-6 bg-[#50514f]">
            <div class="w-[90%] md:w-[75%] border border-whilte p-4 flex flex-col gap-4" v-for="link in userLinks"
                :key="link.userId">
                <p class="text-2xl text-white" v-if="link.name">{{ link.name }}</p>
                <p class="text-2xl text-white" v-else>No title</p>
                <a class="text-[#b4adea] hover:text-white" :href="link.shortenedLink" target="_blank">{{
            link.shortenedLink }}</a>
            </div>
        </section>

        <section v-else>
            <div class="">
                <p>No Links yet!</p>
            </div>
        </section>
    </div>
</template>

<script setup lang="ts">
import DashNav from '../components/DashNav.vue';
import Shortener from '../components/Shortener.vue';
import { toast } from 'vue3-toastify'
import QRCodeVue3 from 'qrcode-vue3';
import { useRouter } from 'vue-router'
import { db, auth, linksRef } from '../utils/firebase';
import {
    onSnapshot, collection,
    addDoc, deleteDoc, doc,
    query, where
} from 'firebase/firestore'
import { onMounted, reactive, ref } from 'vue';

const router = useRouter();

// let userLinks: any = []
// console.log(userLinks);
// const currentUserId = auth.currentUser?.uid;

// // const getLinks = () => {
// onSnapshot(linksRef, (snapshot) => {
//     let links: any = []
//     snapshot.docs.forEach(doc => {
//         links.push({ ...doc.data(), id: doc.id })
//     })
//     userLinks = links.filter((link: any) => link.userId === currentUserId)

// })

// }

// getLinks()


// onMounted(() => {
//     // getLinks()
// })


const userLinks: any = ref([]);

onMounted(() => {
    const userId = auth.currentUser?.uid;
    if (!userId) return; // Exit early if user is not logged in

    const q = query(collection(db, 'links'), where('userId', '==', userId));

    onSnapshot(q, (snapshot) => {
        userLinks.value = snapshot.docs.map(doc => ({ ...doc.data(), id: doc.id }));
    });

    // Clean up the listener when the component is unmounted
    // onUnmounted(unsubscribe);
});

// 
</script>

<style scoped></style>