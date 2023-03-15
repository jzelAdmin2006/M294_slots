<script setup>
import { defineProps } from 'vue'
defineProps({
    src: {
        type: String,
        required: true
    },
    description: {
        type: String,
        required: true
    }
})
</script>

<template>
    <img class="image__img" :src="src" alt="" />
    <p class="image__description">
        {{ description }}
    </p>
</template>