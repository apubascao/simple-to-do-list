<template>
  <header>
    <h1 class="header__title">To-Do List</h1>
  </header> 
</template>

<script>
export default {
  name: 'Header'
}
</script>

<style scoped>
header {
  display: flex;
  justify-content: center;
}
.header__title {
  padding: 5px 10px;
  border-radius: 2em 1em 4em / 0.5em 3em;
  background-color: hsla(191, 71%, 67%, 0.84);
}
</style>