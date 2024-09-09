<script setup>
import { nextTick } from "vue";
import { reactive, ref } from "vue";

const count = ref(0);

const cong = () => count.value++;


const object = reactive({
  count : 1,
  user : {
    age: 20
  },
  array : [1,2,3]
})

const change = ()=>{
  object.count++,
  object.user.age++,
  object.array.push(5,6,7)
}


// nextTick trong Vue 
const count1 = ref(0);

const cong1 = async () => {
  count1.value++;
  console.log(document.getElementById('count1').innerText)
  await nextTick()
  console.log(document.getElementById('count1').innerText)
}

</script>
<template>
  <div>
    <p>{{ count }}</p>
    <button @click="cong">Cộng</button>
    <button @click="count--">Trừ</button>
  </div>

  <div>
    <p>Count: {{ object.count }}</p>
    <p>Age: {{ object.user.age }}</p>
    <p>Array: {{ object.array }}</p>
    <button @click="change">Thay đổi</button>
  </div>


  <!-- nextTick trong Vue  -->
  <div>
    <p id="count1">{{ count1 }}</p>
    <button @click="cong1">Cộng</button>
  </div>
</template>
