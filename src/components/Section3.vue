<template>
    <div class="custom:py-32 py-16 px-5">
        <h2
            class="lg:text-8xl/[105px] text-[46px] leading-[1.1em] tracking-tighter font-medium"
        >
            Design pixel-perfect sites <br class="hidden custom:block" />
            beyond ordinary
        </h2>

        <div class="flex items-start mt-[125px] justify-between">
            <section class="flex-1 custom:max-w-[400px]">
                <ul class="space-y-10">
                    <LayoutGroup>
                        <li
                            v-for="content in contents"
                            :key="content.id"
                            class="flex flex-col text-left relative"
                            :class="{
                                active: isActiveSection(content.id),
                            }"
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
                                    class="circle-dot flex-1 pb-6 text-left relative transition duration-500 ease-linear nth-[3]:bg-red-600"
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
                                            class="text-base/[22px] text-font mb-6 inline-block"
                                            >{{ content.description }}</span
                                        >
                                        <button
                                            v-if="content.id < 2"
                                            class="view-btn relative text-base/7 group text-primary gap-3 hover:gap-5 flex items-center transition-[gap] duration-500 ease-in-out"
                                        >
                                            <span class="font-semibold">
                                                View Details
                                            </span>
                                            <FaArrowRight size="14" />
                                        </button>

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
                class="hidden custom:block bg-primary-300 static rounded-2xl custom:w-[55%] transform-3d -right-5 custom:h-[538px] w-full overflow-hidden"
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
import { FaArrowRight } from "vue-icons-plus/fa";
import { TbPointFilled } from "vue-icons-plus/tb";

const activeContent = ref(0);

const isActiveSection = (id: number) => {
    return activeContent.value === id;
};

const contents = [
    {
        id: 0,
        title: "Advanced typography",
        description:
            "Take full control over your text with precision typography tools. Adjust fonts, spacing, and styles to add more character to your design.",
        img: "https://droip.com/wp-content/uploads/2025/03/advanced-typography.webp",
    },
    {
        id: 1,
        title: "CSS grids and layouts",
        description:
            "Build complex layouts with ease using CSS Grids. Create multi-directional structures, manage spacing, and achieve perfect alignment without limitations.",
        img: "https://droip.com/wp-content/uploads/2025/03/CSS-Grids-Layouts.webp",
    },
    {
        id: 2,
        title: "Adaptive design",
        description:
            "Ensure flawless responsiveness across all devices. Design with adaptive elements that adjust seamlessly to different screen sizes and resolutions.",
        img: "https://droip.com/wp-content/uploads/2025/03/auto-responsive-1.webp",
    },
    {
        id: 3,
        title: "Designed for efficiency",
        description:
            "Streamline your workflow with intuitive tools that simplify layout structuring. Save time while maintaining complete design accuracy and flexibility.",
        img: "https://droip.com/wp-content/uploads/2025/03/Designed-for-Efficiency.webp",
    },
];
</script>

<style scoped>
.circle-fill {
    background-color: var(--color-primary-100);
    /* transition: background-color 400ms ease-in-out; */
}
li::after {
    content: "";
    position: absolute;
    height: calc(100%);
    width: 2px;
    background-color: var(--color-primary-100);
    /* right: calc(100% + 29px + 17px); */
    left: 17px;
    /* transition: height 300ms ease-in-out; */
    top: 38px;
}

li:nth-child(4) .circle-dot {
    padding-bottom: 0px;
}

li:nth-child(4)::after {
    height: 0px;
}

li:nth-child(4).active::after {
    height: calc(100% - 38px);
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
    width: 100px;
}

.image {
    transition: all 700ms ease-in-out 0.2s;
}
</style>
