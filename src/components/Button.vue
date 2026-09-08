<script setup>
const props = defineProps({
  href: {
    type: String,
    default: "#",
  },
  variant: {
    type: String,
    default: "primary",
  },
});
</script>

<template>
  <a
    :href="props.href"
    :class="['primary-button', { light: props.variant === 'light' }]"
  >
    <slot />
  </a>
</template>
