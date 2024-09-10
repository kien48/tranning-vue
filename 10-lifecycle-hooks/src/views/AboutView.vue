<template>
  <div class="about">
    <h1>Time: {{ time }}</h1>
  </div>
</template>

<script setup>
import { onMounted, onUnmounted, ref } from 'vue';

const time = ref(99)

let intervalId = null

onMounted(()=>{
  intervalId = setInterval(()=>{
    time.value--
  },1000)
})

onUnmounted(()=>[
  clearInterval(intervalId)
])
</script>
