<script setup>
defineProps({
    name: {
        type: String,
        required: true,
    },
    label: {
        type: String,
        default: "",
    },
});
</script>

<template>
    <svg class="ui-icon" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round"
        stroke-linejoin="round" :aria-label="label || undefined" :aria-hidden="label ? undefined : 'true'" role="img">
        <path v-if="name === 'arrow-up-right'" d="M5 19 19 5M8 5h11v11" />
        <path v-else-if="name === 'arrow-down'" d="M5 9 12 16 19 9" />
        <path v-else-if="name === 'arrow-up'" d="m5 12 7-7 7 7M12 5v14" />
        <template v-else-if="name === 'menu'">
            <path d="M4 7h16" />
            <path d="M4 12h16" />
            <path d="M4 17h16" />
        </template>
        <template v-else-if="name === 'close'">
            <path d="m6 6 12 12M18 6 6 18" />
        </template>
    </svg>
</template>