<template>
    <div class="input_elem">
      <input @keydown.enter="handler" />
    </div>
  </template>
  
  <script>
  export default {
    methods: {
      handler(event) {
        if (event.key === "Enter") {
          this.$emit("addNewTodo", event.target.value);
          event.target.value = "";
        }
      }
    }
  };
  </script>
  