<template>
<form class="" action="#" method="post" v-on:submit.prevent="bookSubmit(bookTitle, bookAuthor)">
    <input type="text" v-model="book.title" name="title" value="" placeholder="Book Title">
    <input type="text" v-model="book.author" name="author" value="" placeholder="Book Author">
    <input type="text" v-model="book.pages" name="pages" value="" placeholder="Book Pages">
</form>
</template>

<script>
export default {
  name: 'BookForm',
  props: ['book'],
  methods: {
      bookSubmit(bookTitle, bookAuthor) {
          this.$emit('addBook', bookTitle, bookAuthor, bookPages);
      }
  }
}
</script>

<style>
form {
    margin-bottom: 30px;
}
</style>
