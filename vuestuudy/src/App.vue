<template>
  <div>
    <TodoList :todos="todos" />
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue';

import TodoList from "@/components/TodoList.vue";
// const todos = ref(["完成作業", "購物清單", "運動"]);
export default defineComponent({
  setup() {
    const todos = ref([] as string[]);

    return {
      todos,
    };
  },
});
</script>
