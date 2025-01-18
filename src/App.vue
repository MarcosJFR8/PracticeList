<script setup lang="ts">
  import AppHeader from './components/AppHeader.vue';
  import TodoList from './components/TodoList.vue';
</script>

<template>
  <div>
    <AppHeader />
    <TodoList />
  </div>
</template>

<style scoped>
  header{
    border-bottom: #333 solid 1px;
    background-color: #fff;
  }

  header::after{
    content: '';
    display: block;
    height: 1px;
    box-shadow: 0px 0px 10px 0px rgba(0, 0, 0, 0.75);
  }

  h1 .icon{
    font-size: 1rem;
    vertical-align: middle;
  }
</style>
