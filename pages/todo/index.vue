<script setup>
const todos = useState("todos", () => {
  return [];
});
const newTodo = useState(() => "");
const addTodo = () => {
  todos.value.push(newTodo.value);
  newTodo.value = "";
};
const removeTodo = (todo) => {
  const index = todos.value.indexOf(todo);
  todos.value.splice(index, 1);
};
</script>
<template>
  <div>
    Todos
    <div v-for="todo in todos" class="flex flex-row">
      <div @click="removeTodo(todo)">{{ todo }}</div>
    </div>
    <div>
      <input type="text" v-model="newTodo" placeholder="Add todo" />
      <button @click="addTodo">Add</button>
    </div>
  </div>
</template>

<style lang="scss" scoped></style>
