<script setup>
import { computed, ref } from 'vue';

const prop = defineProps({
    type: String,
    message: String,
})

const bgColor = computed(() => {
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

const show = ref(false)

function revealMessage() {
    show.value = true;
}
</script>

<template>
    <div class="w-full rounded-md p-4 text-sm h-14" :class="bgColor" @click="revealMessage">
        <p v-if="show">{{ prop.message }}</p>
        <p v-else class="text-white">Click to show message</p>
    </div>
</template>