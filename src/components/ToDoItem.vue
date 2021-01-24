<template>
  <li>{{ todo.text }}</li>
</template>

<script>
export default {
  name: "ToDoItem",
  props: ['todo']
};
</script>