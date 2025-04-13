<template>
    <div class="h-screen main-container px-5 pt-[208px]">
        <div
            class="flex flex-col gap-4 custom:gap-0 custom:flex-row justify-end custom:justify-between"
        >
            <div class="max-w-[600px] w-full">
                <h2
                    class="lg:text-8xl/[105px] text-[46px]/[1.1em] tracking-tighter font-medium"
                >
                    Create <br class="custom:block hidden" />
                    pixel-perfect accuracy in the atomic level
                </h2>
            </div>
            <div class="image-container flex flex-col gap-5 w-[235px] mx-auto">
                <div v-for="(image, index) in verticalImages">
                    <img
                        class="vertical-image"
                        :src="image"
                        :alt="`vertical slider-${index}`"
                        :key="index"
                    />
                </div>
            </div>
            <div
                class="flex flex-col gap-4.5 justify-end max-w-[316px] w-full order-2 custom:order-3"
            >
                <img class="rotate" :src="rotatorIcon" alt="Rotating icon" />
                <p class="custom:text-2xl/[28px] -tracking-[0.5px] text-lg/6">
                    Create your website from the ground up with complete control
                    over every element, down to the smallest detail.
                </p>
                <button
                    class="view-btn relative text-base/7 text-primary group gap-3 hover:gap-5 flex items-center transition-[gap] duration-500 ease-in-out"
                >
                    <span class="font-semibold">
                        Get Started With Tutorials
                    </span>
                    <FaArrowRight size="14" />
                </button>
            </div>
        </div>
    </div>
</template>

<script setup lang="ts">
import rotatorIcon from "@/assets/icons/rotator.svg";
import { FaArrowRight } from "vue-icons-plus/fa";

const verticalImages = [
    "https://droip.com/wp-content/uploads/2025/03/vertical-slider2.webp",
    "https://droip.com/wp-content/uploads/2025/03/vertical-slider4.webp",
    "https://droip.com/wp-content/uploads/2025/03/vertical-slider3.webp",
    "https://droip.com/wp-content/uploads/2025/03/vertical-slider1.webp",
    "https://droip.com/wp-content/uploads/2025/03/vertical-slider5.webp",
];
</script>

<style scoped>
.image-container {
    height: calc(100vh - 60px);
    overflow-y: scroll;
}

.image-container:nth-child(1),
.image-container:nth-child(2),
.image-container:nth-child(4),
.image-container:nth-child(5) {
    opacity: 0.8;
}

.view-btn::after {
    content: "";
    position: absolute;
    height: 1px;
    background-color: var(--color-primary);
    width: 0px;
    top: 27px;
    transition: width 300ms linear;
}

.view-btn:hover::after {
    width: 200px;
}

.rotate {
    height: 40px;
    margin-right: auto;
    animation: rotator 5s 0.2s infinite forwards;
}

@keyframes rotator {
    from {
        transform-origin: center;
        transform: rotate(0deg);
    }

    to {
        transform: rotate(120deg);
    }
}
</style>
