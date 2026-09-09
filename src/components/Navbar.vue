<script setup>
import { ref } from "vue";

const menuOpen = ref(false);
const floatingHomeStyle = ref({});
const isDraggingHome = ref(false);
const suppressHomeClick = ref(false);

let dragOffset = { x: 0, y: 0 };
let dragStart = { x: 0, y: 0 };

function startHomeDrag(event) {
    const element = event.currentTarget;
    const bounds = element.getBoundingClientRect();

    dragOffset = {
        x: event.clientX - bounds.left,
        y: event.clientY - bounds.top,
    };
    dragStart = { x: event.clientX, y: event.clientY };
    isDraggingHome.value = true;
    suppressHomeClick.value = false;
    element.setPointerCapture(event.pointerId);
}

function moveHome(event) {
    if (!isDraggingHome.value) return;

    const movedX = Math.abs(event.clientX - dragStart.x);
    const movedY = Math.abs(event.clientY - dragStart.y);
    if (movedX > 4 || movedY > 4) suppressHomeClick.value = true;

    const element = event.currentTarget;
    const bounds = element.getBoundingClientRect();
    const left = Math.max(0, Math.min(window.innerWidth - bounds.width, event.clientX - dragOffset.x));
    const top = Math.max(0, Math.min(window.innerHeight - bounds.height, event.clientY - dragOffset.y));

    floatingHomeStyle.value = {
        top: `${top}px`,
        right: "auto",
        bottom: "auto",
        left: `${left}px`,
    };
}

function endHomeDrag(event) {
    if (!isDraggingHome.value) return;

    isDraggingHome.value = false;
    event.currentTarget.releasePointerCapture(event.pointerId);
    if (suppressHomeClick.value) {
        window.setTimeout(() => {
            suppressHomeClick.value = false;
        }, 0);
    }
}

function handleHomeClick(event) {
    if (suppressHomeClick.value) event.preventDefault();
}

const links = [
    { label: "Home", href: "/#home" },
    { label: "About", href: "/#about" },
    { label: "Our work", href: "/#programs" },
    { label: "Our Founder", href: "/founder" },
    { label: "Stories", href: "/founder#founder-story" },
    { label: "Contact", href: "/#contact" },
];
</script>

<template>
    <header class="site-header">
        <a class="brand" href="/#home" aria-label="CBCO home">
            <img src="/images/logo.png" alt="CBCO logo" />
            <span>
                <strong>CBCO</strong>
                <small>Cambodia Banner Charity Organization</small>
            </span>
        </a>

        <button class="menu-toggle" type="button" aria-label="Toggle navigation" :aria-expanded="menuOpen"
            @click="menuOpen = !menuOpen">
            Menu <span>{{ menuOpen ? "×" : "↗" }}</span>
        </button>

        <nav class="desktop-nav" aria-label="Main navigation">
            <a v-for="link in links" :key="link.href" :class="{ 'home-link': link.label === 'Home' }"
                :href="link.href">{{
                    link.label
                }}</a>
        </nav>

        <a class="header-action" href="/#contact">Make an impact <span>↗</span></a>

        <nav v-if="menuOpen" class="mobile-nav" aria-label="Mobile navigation">
            <a v-for="link in links" :key="link.href" :href="link.href" @click="menuOpen = false">{{ link.label }}</a>
        </nav>

        <a class="floating-home" :class="{ 'is-dragging': isDraggingHome }" :style="floatingHomeStyle" href="/#home"
            aria-label="Back to home hero" @pointerdown="startHomeDrag" @pointermove="moveHome" @pointerup="endHomeDrag"
            @pointercancel="endHomeDrag" @click="handleHomeClick">
            <span aria-hidden="true">↑</span>
            Home
        </a>
    </header>
</template>
