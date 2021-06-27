<template>
  <div class="addTodoList">
    <h1 class="title">To-do list</h1>
    <div class="addTodo">
      <input
        class="todoText"
        type="text"
        placeholder="Add Task"
        v-model="newTodo"
      />
      <a class="todoAddButton" @click="addTodo()">
        <font-awesome-icon icon="plus" />
      </a>
    </div>
    <div class="list">
      <todo
        v-for="(todo, index) in todos"
        :key="index"
        :todo="todo"
        :deleteTodo="deleteTodo"
        :index="index"
      />
    </div>
  </div>
</template>

<script>
import Todo from "./Todo";
export default {
  data() {
    return {
      newTodo: "",
      todos: [
        { content: "犬と散歩する", done: true },
        { content: "本を読む", done: false },
      ],
    };
  },
  components: {
    Todo,
  },
  methods: {
    addTodo() {
      this.todos.push({
        content: this.newTodo,
        done: false,
      });
      this.newTodo = "";
    },
    deleteTodo(index) {
      this.todos.splice(index, 1);
    },
  },
};
</script>

<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;700&display=swap");
* {
  font-family: Poppins, sans-serif;
}

.addTodoList {
  display: block;
  text-align: center;
}

.addTodoList .title {
  text-transform: uppercase;
  color: white;
  font-size: 45px;
}

.addTodoList .addTodo {
  display: flex;
  justify-content: center;
}

.addTodoList .addTodo .todoText {
  width: 90%;
  height: 50px;
  outline: none;
  font-size: 18px;
  border-radius: 5px;
  border: none;
  padding: 0 15px;
}

.todoAddButton {
  width: 5%;
  margin-left: 10px;
  padding: 5px 10px;
  font-size: 20px;
  border: 1px solid white;
  color: white;
  border-radius: 5px;
  display: flex;
  align-items: center;
  justify-content: center;
}

.todoAddButton:hover {
  background-color: white;
  color: #9d60c5;
  transition: 0.3s ease-in-out;
}

.list {
  margin: 20px 0px;
}
</style>
