<script setup>
import { computed } from 'vue';

const prop = defineProps({
    type: String
})

const buttonColor = computed(() => {
    if(prop.type == 'regular') {
        return 'bg-blue-600'
    } else if(prop.type == 'happy') {
        return 'bg-green-500'
    }else if(prop.type == 'sad') {
        return 'bg-yellow-400'
    } else {
        return 'bg-red-600'
    }
})
</script>

<template>
    <button type="button" class="px-4 py-1.5 text-sm tracking-wide rounded-sm text-white" :class="buttonColor">
        <slot />
    </button>
</template>