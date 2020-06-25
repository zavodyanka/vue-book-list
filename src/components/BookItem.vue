<template>
    <div class="container">
      <span>{{ book.title }}</span>
      <span>author: {{book.author}}</span>
      <span>{{book.pages}} pages</span>
      <button @click="editBook(index)">Edit</button>
    </div>
</template>

<script>
export default {
  name: 'BookItem',
  props: ['book', 'index'],
  methods: {
    editBook(index) {
      this.$emit('editBook', index);
    }
  }
}
</script>

<style>
span {
  display: block;
  margin: 0 10px;
  min-width: 250px;
}

.container {
  display: flex;
  text-align: left;
  padding: 5px 0;
  justify-content: center;
}
</style>