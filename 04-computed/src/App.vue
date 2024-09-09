<script setup>
import { computed, nextTick } from "vue";
import { reactive, ref } from "vue";

// Sử dụng reactive cho object book
const book = reactive({
  name: 'book 1',
  chapters: []
});

// Hàm thêm chương mới vào sách
const addChapter = () => {
  book.chapters.push('chapter');
};

// Sử dụng computed để xác định sách đã được xuất bản hay chưa
const isPublished = computed(() => {
  return book.chapters.length > 0 ? 'có' : 'không';
});

// Writable computed trong vue

// firstName và lastName cần dùng ref vì đây là các giá trị nguyên thủy
const firstName = ref('Lê Trung');
const lastName = ref('Kiên');

// computed getter và setter để xử lý fullName
const fullName = computed({
  get() {
    return firstName.value + " " + lastName.value;
  },
  set(newValue) {
    [firstName.value, lastName.value] = newValue.split(',');
  }
});

// Hàm đổi tên, sẽ set fullName thành một chuỗi mới
const changeFullName = () => {
  fullName.value = 'Nguyen Van,B';
};
</script>

<template>
  <div>
    <p id="count">book name: {{ book.name }}</p>
    <p id="count">đã xuất bản: {{ isPublished }}</p>
    <button @click="addChapter">Add chapter</button>
  </div>

  <!-- Writable computed trong vue  -->
  <div>
    <p id="count">FullName: {{ fullName }}</p>
    <p>FirstName: {{ firstName }}</p>
    <p>LastName: {{ lastName }}</p>
    <button @click="changeFullName">Đổi tên</button>
  </div>
</template>
