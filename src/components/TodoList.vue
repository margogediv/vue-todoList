<template>
  <div>
    <ul>
      <TodoIteam
      v-for="(todo, i) of todos"
      v-bind:todo="todo"
      v-bind:index="i"
      v-on:remove-todo="removeTodo"
      />
    </ul>
  </div>
</template>

<script>
import TodoIteam from "@/components/TodoIteam";
export default {
  name: "TodoList",
  props: ['todos'],
  components: {TodoIteam},
  comments: {
    TodoIteam
  },
  methods: {
    removeTodo(id) {
      this.$emit('remove-todo', id)
    }
  }
}
</script>

<style scoped>
  ul {
    list-style: none;
    margin: 0;
    padding: 0;
  }
</style>
