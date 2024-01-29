<template>
  <div>
    <AddTodo @addNewTodo="addNewTodo" />
    <TodoList :todos="todos" @removeTodo="removeTodo" @changeTodo="changeTodo" />
  </div>
</template>

<script>
import TodoList from "./components/TodoList.vue";
import AddTodo from "./components/AddTodo.vue";

export default {
  components:{
    TodoList, AddTodo
  },
  data() {
    return {
      todos: [
        { id: 1, title: "Позавтракать", completed: true },
        { id: 2, title: "Почистить огурцы", completed: false },
        { id: 3, title: "Помыть кота", completed: true }
      ]
    };
  },
  methods: {
    removeTodo(id) {
      this.todos = this.todos.filter((elem) => elem.id !== id);
    },
    changeTodo(id) {
      this.todos = this.todos.map((elem) => {
        if (elem.id === id) {
          elem.completed = !elem.completed;
        }
        return elem;
      });
    },
    addNewTodo(title) {
      const newTodo = {
        id: Date.now(),
        completed: false,
        title
      };
      this.todos = [...this.todos, newTodo];
    }
  }
};
</script>
