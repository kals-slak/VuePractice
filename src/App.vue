<template>
  <div>
    <h1>Todo List</h1>
  </div>
  
  <div>
    <form>
      <input v-model="todo">
      <button @click.prevent="addTodo">Add Todo</button>
    </form>
  </div>

  <div class="list">
    <div class="todo" v-for="t in todos" :key="{count}">
      {{t}}
    </div>
  </div>

</template>

<script setup>
import { ref } from 'vue';

let todo= ref("");
let todos= ref([]);
let count= ref(0);
 
const addTodo = ()=>{
  todos.value.push(todo.value);
  todo.value="";
  count++;
}
</script>
