<script setup lang="ts">
import type { ICertificates } from '~/lib/data';

const props = defineProps<{
    certificate: ICertificates 
}>();
</script>

<template>
   <a class="certificate" :href="props.certificate.link" target="_blank">
        <div class="header">
            <div class="title">{{ props.certificate.name }}</div>
            <div class="grantor">{{ props.certificate.grantor }}</div>
        </div>
        <div class="description">{{ props.certificate.description }}</div>
   </a> 
</template>

<style scoped>
.certificate {
    display: flex;
    flex-direction: column;

    gap: 0.5rem;

    background-color: rgba(255, 255, 255, 0.05);

    border: 1px solid rgba(255, 255, 255, 0.1);
    border-radius: 5px;

    transition: background-color 0.25s;
}
.certificate:hover {
    background-color: rgba(255, 255, 255, 0.1);
}
.certificate .header {
    display: flex;
    flex-direction: column;

    background-color: rgba(255, 255, 255, 0.05);

    border-bottom: 1px solid rgba(255, 255, 255, 0.1);

    border-top-left-radius: 5px;
    border-top-right-radius: 5px;

    padding: 0.5rem;
}
.certificate .header .title {
    font-weight: bold;
}
.certificate .header .grantor {
    font-size: 0.8rem;
}
.certificate .description {
    padding: 0.5rem;
}
</style>