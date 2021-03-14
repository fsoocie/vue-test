<template>
  <input type="text" v-model="name">
  <button class="btn" @click="add(name), name=''">Add</button>
</template>

<script>
  export default {
    name: 'Form',
    props: {
      add: Function
  },
    data: () => {
      return {
        name: ''
      }
    },
  }
</script>

<style>

</style>
