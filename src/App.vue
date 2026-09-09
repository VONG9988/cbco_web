<script setup>
import Home from "@/pages/Home.vue";
import Founder from "@/pages/Founder.vue";

const isFounderPage = window.location.pathname === "/founder";
</script>

<template>
  <Founder v-if="isFounderPage" />
  <Home v-else />
</template>
