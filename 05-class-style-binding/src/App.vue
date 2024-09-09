<script setup>
import { computed, ref } from "vue";

// Biến isActive để điều khiển trạng thái active
const isButton = ref(true);
const isActive = ref(true)

const classOpject = computed(()=>({
  active : isActive.value,
  button : isButton.value
}))

const changeButton = () =>{
  isButton.value = !isButton.value
}
</script>

<template>
  <div>
    <!-- Sử dụng cả class "button" và điều kiện cho class "active" -->
    <button :class="classOpject" @click="changeButton">{{ isButton ? 'Active' : "Deactive" }}</button>


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
