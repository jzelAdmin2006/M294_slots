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
    <iframe class=" video__iframe" width="640" height="425" :src="src" title="YouTube video player"
        allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
        allowfullscreen></iframe>
    <div class="video__description">
        {{ description }}
    </div>
</template>