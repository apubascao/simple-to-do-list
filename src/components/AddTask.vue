<template>
  <form class="task-form" @submit.prevent="sendForm">
    <input v-model="taskToAdd" type="text" required>
    <button type="submit">Add Task</button>
  </form>
</template>

<script>
export default {
  name: 'AddTask',
  emits: ['addTask'],
  data() {
    return {
      taskToAdd: ''
    }
  },
  methods: {
    sendForm() {
      this.$emit('addTask', this.taskToAdd)
      this.taskToAdd = ''
    }
  }
}
</script>

<style>
.task-form {
  display: flex;
  justify-content: center;
  align-items: center;
  margin: auto auto 1.875rem auto;
}
.task-form input {
  width: 60%;
  padding: 0.625rem;
  margin: 0.3125rem;
  border: none;
  border-bottom: 3px dashed tomato;
  font-family: 'Caveat Brush', sans-serif;
  font-size: 1.125rem;
}
.task-form input:focus {
  outline: none;
}
.task-form button {
  padding: 0.625rem;
  margin: 0.3125rem;
  font-family: 'Caveat Brush', sans-serif;
  font-size: 1.125rem;
  transform: translateY(-5px) rotate(5deg);
  transition: all 300ms;
  box-shadow: 3px 3px hsla(191, 71%, 67%, 0.84);
  border: 2px solid black;
  border-radius: 0.3125rem ;
  background-color: white;
  cursor: pointer;
}
.task-form button:active {
  transform: translateY(0px);
}
</style>