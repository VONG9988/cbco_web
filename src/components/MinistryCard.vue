<script setup>
defineProps({
  item: {
    type: Object,
    required: true,
  },
});
</script>

<template>
  <article class="focus-card">
    <img :src="item.image" :alt="item.name" />
    <div class="focus-card-body">
      <p class="focus-name">" {{ item.name }} "</p>
      <p class="focus-text">{{ item.text }}</p>
    </div>
  </article>
</template>
