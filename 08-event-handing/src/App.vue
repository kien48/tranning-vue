<!-- eslint-disable vue/no-use-v-if-with-v-for -->
<script setup>
import { ref, reactive } from "vue";

const count = ref(0)

const greet = (event) =>{
  console.log(event)
  alert(`Xin chào ${event.type}`)

}

const sayHi = (name) =>{
  alert(`Xin chào ${name}`)
}

</script>

<template>

<div>
  <h1>Event handling</h1>
  <button @click="count++">Thêm 1</button>
  <p>Count: {{ count }}</p>

  <button @click="greet">Greet</button>
  <button @click.enter.alt="sayHi('Kiên lê')">Say hi</button>



</div>

</template>