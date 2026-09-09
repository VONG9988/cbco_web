<script setup>
import ActivityCard from "@/components/ActivityCard.vue";
import { activities } from "@/data/activities";
</script>

<template>
    <section class="work section" id="programs">
        <div class="section-intro">
            <div>
                <p class="eyebrow">What we do</p>
                <h2>Practical help.<br /><em>Real possibility.</em></h2>
            </div>
            <p>
                Our programs are shaped with communities, designed for everyday life,
                and sustained through relationships.
            </p>
        </div>

        <div class="program-grid">
            <ActivityCard v-for="item in activities" :key="item.number" :item="item" />
        </div>
    </section>
</template>
