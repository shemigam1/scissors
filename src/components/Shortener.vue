<template>
    <div class="w-[90%] md:w-[55%] h-60 flex flex-col items-center text-black">
        <form action="" class="h-full flex flex-col justify-evenly border border-white rounded-md px-4">
            <input class=" placeholder:to-black p-3 rounded-lg" type="text" placeholder="Paste your long url"
                v-model="urlData.longUrl">
            <small v-if="error" class="text-red-500">{{ error }}</small>
            <div class="flex gap-2">
                <input class="p-3 rounded-lg" type="text" placeholder="name">
                <input class="p-3 rounded-lg" type="text" placeholder="alias" v-model="urlData.alias">
            </div>
            <p class="text-black">Slimmed url: {{ shortUrl }}</p>
            <button @click.prevent="shorten" class="bg-[#50514f] py-2 rounded-lg">Trim Url</button>
        </form>
    </div>
</template>

<script setup lang="ts">
import { ref } from 'vue';
import { onMounted, reactive } from 'vue';
import axios, { type AxiosError } from 'axios';
import { toast } from 'vue3-toastify';
import { token } from '../utils/tinyurl';

let shortUrl = ref("")
let urlData = reactive({
    longUrl: "",
    alias: "",
    shortenedLink: "",
})
const linksCreated = reactive([{}])


console.log(urlData);


let error = ref('')
const shorten = async () => {
    error.value = ''
    if (!urlData.longUrl) {
        error.value = 'Please enter a long URL to shorten.'
        return
    }

    if (!/^(http|https):\/\/[^ "]+$/.test(urlData.longUrl)) {
        error.value = 'Please enter a valid URL.'
        return
    }

    try {
        const url = `https://api.tinyurl.com/create`

        const reqBody = {
            url: urlData.longUrl,
            domain: "tinyurl.com",
            alias: urlData.alias,
            description: "string"
        }

        console.log(JSON.stringify(reqBody));
        console.log(urlData.longUrl);
        const response = await axios({
            method: 'post',
            url: `https://api.tinyurl.com/create`,
            data: reqBody,
            headers: {
                accept: `application/json`,
                authorization: `Bearer ${token}`,
                'content-type': `application/json`,
            },
        });
        console.log(response.data.data);
        shortUrl = response.data.data.tiny_url
        urlData.shortenedLink = response.data.data.tiny_url
        linksCreated.push(urlData)
        console.log(shortUrl);

        if (response) {
            toast.success("slimmed link created")
        }


    } catch (err) {
        toast.error("something went wrong, choose another alias")
    }
}

const getHits = async () => {
    const response = await axios({
        method: 'get',
        url: `https://api.tinyurl.com/alias/tinyurl.com/githubblob`,
        headers: {
            accept: `application/json`,
            authorization: `Bearer ${token}`,
            'content-type': `application/json`,
        },
    });
    console.log(response.data);
}

onMounted(() => {
    getHits()
})

</script>

<style scoped></style>