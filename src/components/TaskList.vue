<template>
<div class="task-list">
  <ul v-if="tasks.length" key="">
    <li v-for="(task, index) in tasks" :key="index" @click="onTaskClick(index)">
      <span :class="{ done: task.isDone }">{{ task.title }}</span>
    </li>
  </ul>
  <p v-else>No tasks for today</p>
</div>
</template>

<script>
export default {
  name: 'TaskList',
  props: {
    tasks: {
      type: Array,
      required: true
    }
  },
  methods: {
    onTaskClick(index) {
      this.tasks[index].isDone = !this.tasks[index].isDone
    }
  }
}
</script>

<style>
.task-list {
  margin: 1.875rem;
  font-size: 1.25rem;
}
.task-list ul li {
  cursor: pointer;
}
.task-list ul li:hover {
  color: hsla(191, 71%, 67%, 0.84);
  font-weight: bold;
}
.done {
  text-decoration: 2px line-through wavy tomato;
}

.task-list p {
  text-align: center;
  margin: 2.5rem;
  font-size: 1.25rem;
}
</style>