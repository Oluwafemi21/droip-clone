<template>
    <div class="custom:py-32 py-16 px-5">
        <h2
            class="lg:text-8xl/[105px] custom:text-[46px] text-[11vw] leading-[1.1em] tracking-tighter font-medium"
        >
            Craft engaging and <br class="hidden custom:block" />
            immersive interactions
        </h2>

        <div
            class="flex flex-row-reverse items-start mt-[125px] justify-between"
        >
            <section class="flex-1 custom:max-w-[400px]">
                <ul>
                    <LayoutGroup>
                        <li
                            v-for="content in contents"
                            :key="content.id"
                            class="flex flex-col text-left"
                        >
                            <div
                                @click="activeContent = content.id"
                                class="flex gap-[29px] text-left"
                            >
                                <div class="flex flex-col">
                                    <div
                                        class="size-9 flex items-center justify-center"
                                    >
                                        <div
                                            class="size-6 rounded-full grid place-items-center"
                                            :class="{
                                                'circle-fill': isActiveSection(
                                                    content.id
                                                ),
                                            }"
                                        >
                                            <TbPointFilled
                                                size="14"
                                                class="text-primary"
                                            />
                                        </div>
                                    </div>
                                </div>

                                <button
                                    @click="activeContent = content.id"
                                    :class="{
                                        active: isActiveSection(content.id),
                                    }"
                                    class="circle-dot flex-1 text-left relative pb-11 transition duration-500 ease-linear nth-[3]:bg-red-600"
                                >
                                    <p
                                        class="-tracking-[1.3px] text-2xl/7 custom:text-[32px]/[38px] font-semibold text-font opacity-50 transition-[opacity] duration-500 scale-75 origin-left"
                                        :class="{
                                            'text-black scale-100 opacity-100':
                                                isActiveSection(content.id),
                                        }"
                                    >
                                        {{ content.title }}
                                    </p>
                                    <Motion
                                        v-if="isActiveSection(content.id)"
                                        :layout="true"
                                    >
                                        <span
                                            class="text-base/[22px] text-font my-6 inline-block"
                                            >{{ content.description }}</span
                                        >

                                        <img
                                            class="object-cover h-full max-w-[400px] w-full rounded-2xl mx-auto custom:hidden mt-5"
                                            :src="contents[activeContent].img"
                                            :alt="contents[activeContent].title"
                                        />
                                    </Motion>
                                </button>
                            </div>
                        </li>
                    </LayoutGroup>
                </ul>
            </section>
            <section
                class="hidden custom:block bg-primary-300 static rounded-2xl custom:w-[738px] transform-3d -right-5 custom:h-[538px] w-full overflow-hidden"
            >
                <img
                    class="object-cover h-full w-full rounded-2xl image"
                    :src="contents[activeContent].img"
                    :alt="contents[activeContent].title"
                />
            </section>
        </div>
    </div>
</template>

<script setup lang="ts">
import { LayoutGroup, Motion } from "motion-v";
import { ref } from "vue";
import { TbPointFilled } from "vue-icons-plus/tb";

const activeContent = ref(0);

const isActiveSection = (id: number) => {
    return activeContent.value === id;
};

const contents = [
    {
        id: 0,
        title: "Advanced interaction timeline",
        description:
            "Design smooth, multi-step animations with a timeline-based editor for complete control.",
        img: "https://droip.com/wp-content/uploads/2025/03/Advanced-Interaction-timeline.webp",
    },
    {
        id: 1,
        title: "Custom timing editor",
        description:
            "Fine-tune every interaction to deliver flawless performance by adjusting delays, durations, easing functions, and more. ",
        img: "https://droip.com/wp-content/uploads/2025/03/Custom-Timing-Editor.webp",
    },
    {
        id: 2,
        title: "Advanced triggers",
        description:
            "Trigger animations based on scrolling, hovering, page load, and more for a dynamic experience.",
        img: "https://droip.com/wp-content/uploads/2025/03/Advanced-Triggers.webp",
    },
    {
        id: 3,
        title: "Achieve limitless precision",
        description:
            "Create flawless, interactive designs visually with unmatched accuracy and finesse.",
        img: "https://droip.com/wp-content/uploads/2025/03/Achieve-Limitless-Precision.webp",
    },
];
</script>

<style scoped>
.circle-fill {
    background-color: var(--color-primary-100);
    /* transition: background-color 400ms ease-in-out; */
}

.circle-dot::after {
    content: "";
    position: absolute;
    height: calc(100% - 38px);
    width: 2px;
    background-color: var(--color-primary-100);
    right: calc(100% + 29px + 17px);
    /* transition: height 300ms ease-in-out; */
    bottom: 0px;
}

li:nth-child(4) .circle-dot {
    padding-bottom: 0px;
}

li:nth-child(4) .circle-dot::after {
    height: 0px;
}

li:nth-child(4) .circle-dot.active::after {
    height: calc(100% - 38px);
}

.image {
    transition: all 700ms ease-in-out 0.2s;
}
</style>
