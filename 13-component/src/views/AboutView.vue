<template>
  <div>
    <h1>{{ message }}</h1>
    <button @click="updateMessage">Update Message</button>
    <p>Timer: {{ seconds }} seconds</p>
  </div>
</template>

<script setup>
import { ref, onBeforeMount, onMounted, onBeforeUpdate, onUpdated, onBeforeUnmount, onUnmounted } from 'vue';

// Biến reactive để lưu trữ tin nhắn và số giây
const message = ref("Hello, Vue 3 Lifecycle Hooks!");
const seconds = ref(0);

// Biến lưu timerId cho setInterval
let timerId = null;

// Giai đoạn 1: onBeforeMount - trước khi component được gắn vào DOM
onBeforeMount(() => {
  console.log("onBeforeMount");
});

// Giai đoạn 2: onMounted - ngay sau khi component đã được gắn vào DOM
onMounted(() => {
  console.log("onMounted");
  timerId = setInterval(() => {
    seconds.value++;
  }, 1000);
});

// Giai đoạn 3: onBeforeUpdate - trước khi component được cập nhật khi có sự thay đổi về dữ liệu
onBeforeUpdate(() => {
  console.log("onBeforeUpdate");
});

// Giai đoạn 4: onUpdated - ngay sau khi component được cập nhật xong
onUpdated(() => {
  console.log("onUpdated");
});

// Giai đoạn 5: onBeforeUnmount - trước khi component bị gỡ khỏi DOM
onBeforeUnmount(() => {
  console.log("onBeforeUnmount");
});

// Giai đoạn 6: onUnmounted - ngay sau khi component bị gỡ khỏi DOM
onUnmounted(() => {
  console.log("onUnmounted");
  clearInterval(timerId); // Dọn dẹp bộ đếm thời gian
});

// Hàm để cập nhật tin nhắn khi người dùng nhấn nút
function updateMessage() {
  message.value = "Message updated!";
  console.log("Message updated.");
}
</script>
