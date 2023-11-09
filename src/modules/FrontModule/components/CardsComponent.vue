<template>
    <div 
        class="overflow-hidden mr-10 min-w-min flex flex-col container last:mr-0"
        v-for="card in arr_cards"
        :key="card.id"
    >
        <div class="h-72 w-60 xl:h-96 border-transparent rounded shadow-[0_3px_10px_rgb(0,0,0,0.2)]">
            <img class="w-full h-full rounded border-transparent image" :src="card.img" alt="">
        </div>
        <div class="mt-2 text-left">
            <p class="text-xl font-sans">— {{ card.name }}</p>
            <p class="font-sans text-xs text-gray-300">{{ card.description }}</p>
        </div>
    </div>
</template>

<script setup>
import { ref, onMounted, nextTick } from 'vue'
import { gsap } from 'gsap'
import { ScrollTrigger } from 'gsap/ScrollTrigger'

gsap.registerPlugin(ScrollTrigger)

const arr_cards = ref([
    {
        id: 1,
        name: 'Edoardo Botez',
        description: "A black and white photo of a wall with square windows.",
        img: 'https://images.unsplash.com/photo-1673286409996-20c76682842c?auto=format&fit=crop&q=80&w=2853&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D'
    },
    {
        id: 2,
        name: 'Mak',
        description: "Some stairs in a building.",
        img: 'https://images.unsplash.com/photo-1698764474376-30ae259d7abb?auto=format&fit=crop&q=80&w=2787&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D'
    },
    {
        id: 3,
        name: 'Andrey Zvyagintsev',
        description: "A house on top of a mountain surrounded by trees.",
        img: 'https://images.unsplash.com/photo-1695977110890-9e052bc189ec?auto=format&fit=crop&q=80&w=2787&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D'
    },
    {
        id: 4,
        name: 'Jared Subia',
        description: 'A basketball hoop with a blue sky in the background.',
        img: 'https://images.unsplash.com/photo-1695467502897-8114d6701d14?auto=format&fit=crop&q=80&w=2787&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D'
    },
    {
        id: 5,
        name: 'Elliot Voilmy',
        description: 'A lifeguard stand on the beach with a life guard on it.',
        img: 'https://images.unsplash.com/photo-1698402532181-78b834538a86?auto=format&fit=crop&q=80&w=2854&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D'
    },
    {
        id: 6,
        name: 'Lena Polishko',
        description: 'A cactus in front of a building with a sky background.',
        img: 'https://images.unsplash.com/photo-1696075619078-6cb640d329ec?auto=format&fit=crop&q=80&w=2793&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D'
    },
    {
        id: 7,
        name: 'Masood Aslami',
        description: 'A red house sitting on top of a cliff.',
        img: 'https://images.unsplash.com/photo-1698252687043-f22f8d0b8a06?auto=format&fit=crop&q=80&w=2035&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D'
    },
    {
        id: 8,
        name: 'Jake Noble',
        description: 'A tall building with balconies and a traffic light.',
        img: 'https://images.unsplash.com/photo-1698863984285-7e8f781f6b7e?auto=format&fit=crop&q=80&w=2788&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D'
    }
]);

// const container = ref();

onMounted(async () => {
    await nextTick();

    const first_section = document.querySelector('.first-section');
    
    let photos = gsap.utils.toArray('.container');

    gsap.to('.container', {
        scrollTrigger: {
            trigger: first_section,
            start: 'top top',
            end: () => '+=' + document.querySelector('.container').offsetWidth,
            scrub: 1,
            pin: true,
            pinSpacing: true,
            snap: 1 / (photos.length - 1),
            // snap: 1
        },
        xPercent: -100 * (photos.length - 1),
    });
})
</script>

<style>

</style>