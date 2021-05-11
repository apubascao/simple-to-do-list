<template>
<div class="container">
  <Header />
  <AddTask v-on:addTask="onAddTask" />
  <TaskList :tasks="tasks" />
</div>
</template>

<script>
import Header from './components/Header'
import AddTask from './components/AddTask'
import TaskList from './components/TaskList'

export default {
  name: 'App',
  components: {
    Header,
    AddTask,
    TaskList
  },
  data() {
    return {
      tasks: []
    }
  },
  methods: {
    onAddTask(title) {
      this.tasks.push({ title, isDone: false })
    }
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Caveat+Brush&display=swap');

body {
  padding: 20px;
  font-family: 'Caveat Brush', sans-serif;
  background-color: tomato;
}
.container {
  overflow: auto;
  max-width: 31.25rem;
  min-height: 18.75rem;
  margin: auto;
  padding: 1.875rem;
  border-radius: 20px;
  box-shadow: 0 14px 28px rgba(0,0,0,0.25), 0 10px 10px rgba(0,0,0,0.22);
  background-color: white;
}
.btn {
  display: inline-block;
  background: #000;
  color: #fff;
  border: none;
  padding: 10px 20px;
  margin: 5px;
  border-radius: 5px;
  cursor: pointer;
  text-decoration: none;
  font-size: 15px;
  font-family: inherit;
}
.btn:focus {
  outline: none;
}
.btn:active {
  transform: scale(0.98);
}
.btn-block {
  display: block;
  width: 100%;
}
</style>
