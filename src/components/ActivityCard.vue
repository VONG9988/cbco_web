<script setup>
defineProps({
    item: {
        type: Object,
        required: true,
    },
});
</script>

<template>
    <article class="program">
        <div class="program-image">
            <img :src="item.image" :alt="item.title" />
            <span>{{ item.number }}</span>
        </div>
        <div class="program-body">
            <h3>{{ item.title }}</h3>
            <p>{{ item.text }}</p>
            <a :href="item.href || '#contact'" :aria-label="`Learn more about ${item.title}`">
                Learn more <span>↗</span>
            </a>
        </div>
    </article>
</template>
