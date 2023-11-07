<template>
    <div>
      <h2>代辦清單</h2>
      <input v-model="newTodo" @keyup.enter="addTodo" placeholder="新增代辦事項" />
      <ul>
        <li v-for="(todo, index) in todos" :key="index">{{ todo }}</li>
      </ul>
    </div>
  </template>
  
  <script lang="ts">
  import { defineComponent, PropType } from 'vue';
  
  export default defineComponent({
    props: {
      todos: {
        type: Array as PropType<string[]>,
        required: true,
      },
    },
    data() {
      return {
        newTodo: '',
      };
    },
    methods: {
      addTodo() {
        if (this.newTodo) {
          this.todos.push(this.newTodo);
          this.newTodo = '';
        }
      },
    },
  });
  </script>
  