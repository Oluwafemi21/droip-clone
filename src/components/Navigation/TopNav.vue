<template>
    <div class="flex items-center justify-between py-2 gap-16">
        <img src="@/assets/droip.svg" alt="Droip logo" />
        <div
            class="custom:flex items-center justify-between flex-1 hidden h-11"
        >
            <!-- navigation buttons -->
            <div class="flex items-center gap-3.5 text-[14px]">
                <div
                    class="group p-2.5 flex items-center cursor-pointer first:text-black nth-[2]:text-black text-font-grey"
                    :class="{ 'gap-1': hasDropdown }"
                    v-for="{ label, hasDropdown, links } in navigationLinks"
                    :key="label"
                >
                    <a href="#" class="font-medium capitalize">
                        {{ label }}
                    </a>
                    <BsChevronDown
                        size="12"
                        class="group-hover:rotate-180 transition-rotate ease-linear duration-300"
                        v-if="hasDropdown"
                    />

                    <div class="bg-purple rounded-lg"></div>
                </div>
            </div>
            <!-- auth buttons -->
            <div class="flex items-center gap-4">
                <button class="p-2.5 text-font hover:text-black">Login</button>
                <div>
                    <button class="btn-primary">Get Started</button>
                </div>
            </div>
        </div>
        <button @click="toggleDropdown" class="*:text-primary custom:hidden">
            <HiOutlineMenu v-if="!showDropdown" />
            <HiX v-else />
        </button>
    </div>
</template>

<script setup lang="ts">
import { BsChevronDown } from "vue-icons-plus/bs";
import { HiOutlineMenu, HiX } from "vue-icons-plus/hi";
import accessibilityIcon from "@/assets/icons/accessibility.svg";
import contentIcon from "@/assets/icons/content.svg";
import editorIcon from "@/assets/icons/editor.svg";
import figmaIcon from "@/assets/icons/figma.svg";
import formBuilderIcon from "@/assets/icons/form-builder.svg";
import gridIcon from "@/assets/icons/grid.svg"; // or grids.svg if you prefer
import interactionIcon from "@/assets/icons/interaction.svg";
import mediaIcon from "@/assets/icons/media.svg";
import popupIcon from "@/assets/icons/popup.svg";
import seoIcon from "@/assets/icons/seo.svg";
import typoIcon from "@/assets/icons/typo.svg";
import blogIcon from "@/assets/icons/blog.svg";
import documentationIcon from "@/assets/icons/documentation.svg";
import clockIcon from "@/assets/icons/clock.svg";
import messageIcon from "@/assets/icons/message.svg";
import featureIcon from "@/assets/icons/feature.svg";
import contactIcon from "@/assets/icons/contact.svg";
import { ref } from "vue";

const showDropdown = ref(false);
const navigationLinks = [
    {
        label: "home",
        hasDropdown: false,
    },
    {
        label: "product",
        hasDropdown: true,
        links: [
            {
                title: "Editor",
                description: "Effective Visual Builder",
                icon: editorIcon,
            },
            {
                title: "Interaction & Animation",
                description: "Create interactive experiences",
                icon: interactionIcon,
            },
            {
                title: "Grids & Layouts",
                description: "Structure more easily",
                icon: gridIcon,
            },
            {
                title: "Media Manager",
                description: "Manage & edit site assets",
                icon: mediaIcon,
            },
            {
                title: "Typography",
                description: "Customize your branding",
                icon: typoIcon,
            },
            {
                title: "SEO",
                description: "Optimize your SEO workflow",
                icon: seoIcon,
            },
            {
                title: "Form Builder",
                description: "Design any web forms",
                icon: formBuilderIcon,
            },
            {
                title: "Accessibility",
                description: "Accessible to everyone",
                icon: accessibilityIcon,
            },
            {
                title: "Pop-up Builder",
                description: "Build pop-ups visually",
                icon: popupIcon,
            },
            {
                title: "Figma to Droip",
                description: "Turn static design into live pages",
                icon: figmaIcon,
            },
            {
                title: "Content Manager",
                description: "Centralized dynamic content management",
                icon: contentIcon,
            },
        ],
    },
    {
        label: "resources",
        hasDropdown: true,
        links: [
            {
                title: "Droip Blogs",
                description: "Explore what's happening",
                icon: blogIcon,
            },
            {
                title: "Documentation",
                description: "Learn from documentation",
                icon: documentationIcon,
            },
            {
                title: "Release Notes",
                description: "Check what's new",
                icon: clockIcon,
            },
        ],
    },
    {
        label: "support",
        hasDropdown: true,
        links: [
            {
                title: "Get support",
                description: "Fix your issues with our experts",
                icon: messageIcon,
            },
            {
                title: "Feature Request",
                description: "Let us know what's missing",
                icon: featureIcon,
            },
            {
                title: "Contact",
                description: "Contact for query",
                icon: contactIcon,
            },
        ],
    },
    {
        label: "pricing",
        hasDropdown: false,
    },
];

const toggleDropdown = () => {
    showDropdown.value = !showDropdown.value;
};
</script>

<style scoped></style>
