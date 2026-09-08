<script setup>
defineProps({
  eyebrow: {
    type: String,
    default: "",
  },
  title: {
    type: String,
    required: true,
  },
  align: {
    type: String,
    default: "left",
  },
});
</script>

<template>
  <div class="section-heading" :class="align">
    <p v-if="eyebrow" class="eyebrow">{{ eyebrow }}</p>
    <h2 v-html="title"></h2>
  </div>
</template>
