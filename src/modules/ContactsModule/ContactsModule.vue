<template>
    <div class="px-5 py-10 md:px-16 md:py-10 w-full">
        <div class="flex flex-col md:justify-start md:align-start leading-3 overflow-hidden contact_container">
            <p class="text-2xl text-center md:text-left md:text-5xl lg:text-6xl uppercase font-bold tracking-tighter font-sans">Bruce James Dela Cruz</p>
            <p class="text-2xl text-center md:text-left md:text-5xl lg:text-6xl uppercase font-bold tracking-tighter font-sans">Web Developer</p>
        </div>
    </div>
</template>

<script setup>
import { gsap } from 'gsap'
import { ScrollTrigger } from 'gsap/ScrollTrigger'
import { CustomEase } from 'gsap/CustomEase'
import { onMounted, nextTick } from 'vue'

gsap.registerPlugin(ScrollTrigger);
gsap.registerPlugin(CustomEase);

onMounted(async () => {
    await nextTick();

    const container = document.querySelector('.contact-container');

    // gsap.to('.contact_container', {
    //     scrollTrigger: {
    //         trigger: container,
    //         start: 'top bottom',
    //         end: () => '+=3500',
    //     },
    //     x: 400,
    //     duration: 2
    // })
    gsap.from('.contact_container', {
        scrollTrigger: {
            trigger: container,
            start: 'center center',
        },
        x: -800,
        ease: CustomEase.create('ease-in-out', 'M0,0 C0.69,-0.04 0.25,0.99 1,1'),
        duration: 1.5
    })
});
</script>

<style>

</style>