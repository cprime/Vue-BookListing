<template>
  <div class="booklist">
    <h1>{{ title }}</h1>
    <ul>
      <book-item v-for="book in books" :key="book.title" :book="book" />
    </ul>
    <book-form @addBook="appendBook" />
  </div>
</template>

<script>
import BookItem from "./BookItem";
import BookForm from "./BookForm";

export default {
  name: "BookList",
  data() {
    return {
      title: "All Books",
      books: [
        { title: "Self-Reliance", author: "Ralph Waldo Emerson" },
        { title: "American Gods", author: "Neil Gaiman" },
        { title: "Amusing Ourselves to Death", author: "Neil Postman" }
      ]
    };
  },
  methods: {
    appendBook: function(bookTitle, bookAuthor) {
      this.books.push({ title: bookTitle, author: bookAuthor });
    }
  },
  components: {
    BookItem,
    BookForm
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1,
h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
</style>
