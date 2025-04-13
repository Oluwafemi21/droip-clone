<template>
    <div class="accordion h-60 border border-amber-700 text-font">
        <button @click="isOpen = !isOpen" class="accordion-toggle">
            {{ isOpen ? "Close" : "Open" }}
        </button>

        <Motion
            v-if="isOpen"
            tag="div"
            class="accordion-content overflow-hidden"
            :initial="{ height: 0, opacity: 0 }"
            :transition="{
                type: 'spring',
                stiffness: 260,
                damping: 20,
            }"
        >
            <div ref="content" class="p-4 text-black bg-gray-100 rounded">
                <p>This is the accordion content with a smooth animation!</p>
            </div>
        </Motion>
    </div>
</template>

<script setup lang="ts">
import { ref, onMounted } from "vue";
import { Motion } from "motion-v";

const isOpen = ref(false);
const content = ref<HTMLElement | null>(null);
const autoHeight = ref(0);

const updateAutoHeight = () => {
    if (content.value) {
        autoHeight.value = content.value.scrollHeight;
    }
};

onMounted(updateAutoHeight);
</script>

<style scoped>
.accordion-toggle {
    padding: 0.75rem 1rem;
    background-color: #2563eb;
    color: white;
    border: none;
    border-radius: 0.375rem;
    cursor: pointer;
}
</style>
