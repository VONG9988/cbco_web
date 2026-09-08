<script setup>
import { ref } from "vue";

const menuOpen = ref(false);

const links = [
  { label: "About", href: "#about" },
  { label: "Our work", href: "#programs" },
  { label: "Stories", href: "#stories" },
  { label: "Contact", href: "#contact" },
];
</script>

<template>
  <header class="site-header">
    <a class="brand" href="#home" aria-label="CBCO home">
      <img src="/images/logo.png" alt="CBCO logo" />
      <span>
        <strong>CBCO</strong>
        <small>Cambodia Banner Charity Organization</small>
      </span>
    </a>

    <button
      class="menu-toggle"
      type="button"
      aria-label="Toggle navigation"
      :aria-expanded="menuOpen"
      @click="menuOpen = !menuOpen"
    >
      Menu <span>{{ menuOpen ? "×" : "↗" }}</span>
    </button>

    <nav class="desktop-nav" aria-label="Main navigation">
      <a v-for="link in links" :key="link.href" :href="link.href">{{
        link.label
      }}</a>
    </nav>

    <a class="header-action" href="#contact">Make an impact <span>↗</span></a>

    <nav v-if="menuOpen" class="mobile-nav" aria-label="Mobile navigation">
      <a
        v-for="link in links"
        :key="link.href"
        :href="link.href"
        @click="menuOpen = false"
        >{{ link.label }}</a
      >
    </nav>
  </header>
</template>
