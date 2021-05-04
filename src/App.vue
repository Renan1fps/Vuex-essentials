<template>
  <div>
    <ul>
      <li v-for="todo in $allTodos" :key="todo.id">
        {{ todo.text }}
      </li>
      <h1></h1>
    </ul>
  </div>
</template>

<script>
export default {
  computed: {
    $allTodos() {
      return this.$store.getters.$doneTodos
    }
  },
  created() {
    this.$store.dispatch('fetchTodos')
  }
}
</script>

