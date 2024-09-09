<script setup>
import { ref } from "vue";

// Biến isActive để điều khiển trạng thái active
const isButton = ref(true);
const isActive = ref(true)
</script>

<template>
  <div>
    <!-- Sử dụng cả class "button" và điều kiện cho class "active" -->
    <button :class="{'button' : isButton, 'active' : isActive}">Active</button>
  </div>
</template>

<style>
/* Định nghĩa kiểu cho nút */
.button {
  border: none;
  background: lightcyan;
  color: dodgerblue;
  padding: 10px 14px;
  border-radius: 6px;
  cursor: pointer;
}

.button:hover {
  background: gold;
}

/* Định nghĩa kiểu cho class "active" */
.active {
  background: lightcyan;
  color: dodgerblue;
}

.active:hover {
  background: dodgerblue;
}
</style>
