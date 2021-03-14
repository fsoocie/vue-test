<template>
  <li class="item">
    <div>
      <input type="checkbox" v-model="complete">
      <strong :style="{textDecoration: complete ? 'line-through' : 'none'}"> {{ todo.index }} </strong> &nbsp;
      <span :style="{textDecoration: complete ? 'line-through' : 'none'}">{{ todo.text }}</span>
    </div>
    <button @click="remove(todo.index)">&times;</button>
  </li>
</template>

<script>
  export default {
    name: 'Todo',
    props: {
      todo: {
        text: String,
        index: Number
      },
      remove: Function
    },
    data: () => ({
      complete: false
    })
  }
</script>

<style>
  .item {
    list-style: none;
    display: flex;
    justify-content: space-between;
  }
</style>
