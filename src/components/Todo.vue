<template>
  <div class="container">
    <div class="todo">
      <input type="checkbox" v-model="todo.done" />
      <span :class="{ done: todo.done }">
        {{ todo.content }}
      </span>
      <a class="deleteButon" href="#" @click.prevent="deleteTodo(index)">
        <font-awesome-icon icon="trash" />
      </a>
    </div>
  </div>
</template>

<script>
export default {
  props: ["todo", "index", "deleteTodo"],
};
</script>

<style scoped>
.container {
  display: flex;
  flex-direction: column;
}

.todo {
  color: white;
  border: 1px solid white;
  padding: 10px;
  border-radius: 5px;
  margin-top: 10px;
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.todo span {
  max-width: 80%;
  word-wrap: break-word;
  font-size: 20px;
}

.todo span.done {
  color: rgba(0, 0, 0, 0.336);
}

.todo input {
  width: 20px;
  height: 20px;
}

.todo .deleteButon {
  color: white;
  font-size: 20px;
}
</style>
