<template>
<div>
  <h1>{{ title }}</h1>
  <book-form @addBook='appendBook' :book="editedBook"></book-form>
  <book-item v-for="(book, index) in books" :key="book.id" :book="book" :index="index" @editBook=changeBook(index)></book-item>
</div>
</template>

<script>
import BookItem from './BookItem';
import BookForm from './BookForm';

export default {
  name: 'BookList',
  data() {
    return {
      title: "All Books",
      books: [
        {id: 1, title: 'Jak się dawniej listy pisały', author: 'Józef Ignacy Kraszewski', pages: 23},
        {id: 2, title: 'Nad brzegiem Renu stali...', author: 'Eliza Orzeszkowa', pages: 4},
        {id: 3, title: 'Szkice piórkiem', author: 'Andrzej Bobkowski', pages: 552},
      ],
      editing: false,
      editedBook: {},
    }
  },
  methods: {
    changeBook(index) {
      this.editedBook = this.books[index];
    }
  },
 components: {
   BookItem,
   BookForm
 },
}
</script>

<style>
h1, h2 {
  font-weight: normal;
}
</style>
