<template>
    <div class="pt-16">
        <p
            class="font-semibold w-fit rounded-full bg-primary-300 py-2.5 px-6 text-lg/[22px] mt-1 mb-12"
        >
            No-Code WordPress Site Builder
        </p>

        <div class="mb-24">
            <h1
                class="text-8xl/[105px] tracking-tighter capitalize font-semibold"
            >
                break limits. <br class="hidden lg:block" />
                build <span class="text-primary">anything.</span>
                <br class="hidden lg:block" />
                no code needed.
            </h1>

            <div class="grid">
                <div
                    class="rounded-xl bg-primary-200 text-lg/[25px] text-font-grey p-6 pb-20"
                >
                    <p>
                        Droip is a no-code, drag-and-drop WordPress builder that
                        simplifies website creation with powerful capabilities.
                    </p>
                </div>
                <div
                    class="rounded-xl text-primary gap-1.5 bg-primary-200 text-base/[30px] flex items-center justify-center hover:bg-primary-300 mt-1 mb-2"
                >
                    <p>Watch Intro</p>
                    <img :src="videoIcon" alt="video icon" />
                </div>

                <button
                    class="btn-primary text-lg/[28px] group flex items-center justify-center gap-1.5"
                >
                    <p class="text-lg/[28px]">Get started with Droip</p>
                    <HiOutlineChevronRight class="group-hover:hidden" />
                    <HiArrowRight class="group-hover:block hidden" />
                </button>
            </div>
        </div>
    </div>
</template>

<script setup lang="ts">
import videoIcon from "@/assets/icons/video.svg";
import { HiArrowRight, HiOutlineChevronRight } from "vue-icons-plus/hi";
</script>

<style scoped></style>
