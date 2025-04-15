<template>
    <div
        class="bg-primary-200 custom:rounded-3xl custom:py-12 custom:pl-12 py-8 custom:pr-0 px-4.5 flex flex-col custom:flex-row gap-x-10"
    >
        <div class="max-w-xs w-full flex flex-col justify-between">
            <h3
                class="text-2xl leading-7 font-semibold custom:leading-[30px] mb-8"
            >
                {{ props.card.title }}
            </h3>

            <div class="pb-4.5 space-y-4.5">
                <p class="custom:text-2xl/7 text-base leading-5 tracking-tight">
                    {{ props.card.description }}
                </p>
                <button
                    class="view-btn relative text-base/7 group gap-3 hover:gap-5 flex items-center transition-[gap] duration-500 ease-in-out"
                >
                    <span class="font-semibold text-primary">
                        View Details
                    </span>
                    <FaArrowRight size="14" />
                </button>
            </div>
        </div>

        <img
            class="rounded-l-[9px] ml-auto object-cover custom:max-w-[874px] custom:h-[467px] w-[400px] h-[200px] flex-1"
            :src="props.card.image"
            :alt="props.card.title"
        />
    </div>
</template>

<script setup lang="ts">
import { FaArrowRight } from "vue-icons-plus/fa";

const props = defineProps({
    card: {
        type: Object,
        default: () => {},
        required: true,
    },
});
</script>

<style scoped>
.view-btn::after {
    content: "";
    position: absolute;
    height: 2px;
    background-color: var(--color-primary);
    width: 0px;
    top: 27px;
    transition: width 300ms linear;
}

.view-btn:hover::after {
    width: 100px;
}
</style>
