<template>
    <div class="bg-black h-[200vh] overflow-y-scroll custom:py-32 py-16">
        <div class="main-container px-5">
            <h2
                class="text-white lg:text-8xl/[105px] text-[46px]/[1.1em] tracking-tighter capitalize font-semibold mb-24"
            >
                Scale your <br class="hidden lg:block" />
                business with
            </h2>

            <Card v-for="card in cards" :card="card" :key="card.title" />
        </div>
    </div>
</template>

<script setup lang="ts">
import Card from "./ScrollPin/Card.vue";
const cards = [
    {
        title: "Content Manager",
        description:
            "Handle dynamic data with the built-in content manager. Link data dynamically to any part of your website.",
        image: "https://droip.com/wp-content/uploads/2025/03/CMS1.webp",
    },
    {
        title: "Media Manager",
        description:
            "Organize and edit all media assets, including SVGs, Lottie, and icons, with the built-in image and shape editor.",
        image: "https://droip.com/wp-content/uploads/2025/03/Media-Manager.webp",
    },
    {
        title: "SEO",
        description:
            "Dynamically update SEO content across pages to optimize your website's search performance.",
        image: "https://droip.com/wp-content/uploads/2025/03/dymanic-seo2-1.webp",
    },
];
</script>

<style scoped></style>
