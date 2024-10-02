<script setup>
import { ref } from 'vue'
import Todo from './Todo.vue'
import AddTodo from './AddTodo.vue'

const todos = ref([
  {'id': 1, 'title': 'Nhecos', 'status': true},
  {'id': 2, 'title': 'Lorem', 'status': true},
  {'id': 3, 'title': 'Ipsum', 'status': true},
  {'id': 4, 'title': 'Coiso', 'status': false},
])

const title = ref('')

const addItem = function (event) {
  if( '' == title.value )return false;
  let id = Math.random();
  return this.todos.push({'id': id, 'title': title.value, 'status': true});
}

const changeItemStatus = function (id, status) {
  const index = this.todos.findIndex(item => {
    if (id === item.id) return item.status = !status
  })
}
</script>

<template>
  <h1>Todos</h1>
    <AddTodo v-model:title="title" @add-item="(event) => addItem(event)"></AddTodo>

  <ul class="list">
    <Todo v-for="item in todos" :key="item.id" :title="item.title" :status="item.status" @change-status="changeItemStatus(item.id, item.status)" :class="{ 'lnthrough': !item.status }" />
  </ul>
</template>

<style scoped>
.list {width:100%; list-style: circle;}
</style>