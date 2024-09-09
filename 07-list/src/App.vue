<!-- eslint-disable vue/no-use-v-if-with-v-for -->
<script setup>
import { ref, reactive } from "vue";

const shoppingItems = ref([
  {
    name: 'apple', price: 7
  },
  {
    name: 'banana', price: 8
  }
])

const user = ref({
  name : 'kEKEE',
  age  : 19,
})

const users = ref(
 [ {
  name : "Kiên",
  age: 20,
  active : false
    },

    {
  name : "Cường",
  age: 20,
  active: true
    },]
)


const todos = reactive([
  {
    id : 1,
    text: "learn vuejs"
  },
  {
    id : 2,
    text: 'learn java'
  }
])

const newTodo = ref('')

const addTodo = () =>{
  if(newTodo.value.trim() === "") return
  const todo = {
    id : todos.length + 1,
    text : newTodo.value
  }
  todos.push(todo)
  newTodo.value = ""

}

</script>

<template>

<div>
  <ul>
    <li v-for="item in shoppingItems" :key="item.name">
      {{ item.name }} - {{ item.price }}
    </li>

    <li v-for="i in 10" :key="i">{{ i }}</li>
  </ul>
</div>

<div>
   <li v-for="(key, value, index) in user" :key="index">
       {{ key }}: {{ value }} ({{ index }})
   </li>
</div>

<ul>
<template v-for="user in users" >
    <li v-if="user.active" :key="user">
      {{ user.name }} - {{ user.age }} - {{ user.active ? 'Đã kích hoạt' : 'Chưa kích hoạt'}}
    </li>
  </template>
</ul>

  <div>
    <input type="text" name="" id="" v-model="newTodo" @keyup.enter="addTodo">
    <button @click="addTodo">Add todo</button>
    <ul>
      <li v-for="todo in todos" :key="todo.id">
           {{ todo.text }} - {{ todo.id }}
      </li>
    </ul>
  </div>

</template>