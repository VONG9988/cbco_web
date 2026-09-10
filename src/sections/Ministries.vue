<script setup>
import MinistryCard from "@/components/MinistryCard.vue";
import { focusGroups } from "@/data/ministries";
</script>

<template>
    <section class="focus-section" id="serve">

        <div v-for="group in focusGroups" :key="group.title" class="focus-group">
            <h3 class="text-center font-bold btn">Our Works</h3>
            <div v-if="group.title" class="focus-group-label">{{ group.title }}</div>

            <div class="focus-grid">
                <MinistryCard v-for="item in group.items" :key="item.name" :item="item" />
            </div>

            <p v-if="group.paragraph" class="focus-paragraph">
                {{ group.paragraph }}
            </p>
        </div>
    </section>
</template>
