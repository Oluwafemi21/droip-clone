<template>
    <div class="pt-16 custom:pb-24 pb-[60px] px-5">
        <p
            class="font-semibold w-fit rounded-full bg-primary-300 py-2.5 px-6 text-lg/[22px] mt-1 mb-12"
        >
            No-Code WordPress Site Builder
        </p>

        <div class="flex gap-12 justify-between flex-col custom:flex-row">
            <h1
                class="lg:text-8xl/[105px] text-[46px]/[1.1em] tracking-tighter capitalize font-semibold"
            >
                break limits. <br class="hidden lg:block" />
                build <span class="text-primary">anything.</span>
                <br class="hidden lg:block" />
                no code needed.
            </h1>

            <div class="grid gap-1 custom:max-w-[316px]">
                <div
                    class="rounded-xl md:bg-primary-200 text-lg/[25px] text-font-grey md:p-6 md:pb-20"
                >
                    <p>
                        Droip is a no-code, drag-and-drop WordPress builder that
                        simplifies website creation with powerful capabilities.
                    </p>
                </div>
                <div
                    class="px-6 py-[11px] h-11 font-semibold rounded-[18px] text-primary gap-1.5 bg-primary-200 text-base/[30px] flex items-center justify-center hover:bg-primary-300"
                >
                    <p>Watch Intro</p>
                    <img :src="videoIcon" alt="video icon" />
                </div>

                <div class="h-[52px] flex items-center justify-center">
                    <button
                        class="cc relative w-full h-11 rounded-[18px] hover:gap-2.5 hover:h-[52px] transition-[height] base-transition btn-primary text-lg/[28px] group flex items-center justify-center gap-1.5"
                    >
                        <p class="text-lg/[28px]">Get started with Droip</p>
                        <div class="chevron">
                            <HiOutlineChevronRight size="22" class="chevy" />
                        </div>
                    </button>
                </div>
            </div>
        </div>
    </div>
</template>

<script setup lang="ts">
import videoIcon from "@/assets/icons/video.svg";
import { HiOutlineChevronRight } from "vue-icons-plus/hi";
</script>

<style scoped>
.cc:hover > .chevron::after {
    transform: translateX(2px);
    display: block;
}

.cc:hover > .chevron > .chevy {
    transition-delay: 10ms;
    transform: translateX(0px);
}

.chevron::after {
    content: "";
    position: absolute;
    height: 2.5px;
    background-color: white;
    border-radius: 4px;
    width: 12px;
    bottom: 48%;
    top: 48%;
    transform: translateY(2px);
    transition: transform 500ms ease-in-out 0.1s;
    display: none;
}
</style>
