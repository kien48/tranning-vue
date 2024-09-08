<script setup>
import { ref } from "vue";

const count = ref(0);

const cong = () => count.value++;
</script>
<template>
  <div>
    <p>{{ count }}</p>
    <button @click="cong">Cộng</button>
  </div>
</template>
