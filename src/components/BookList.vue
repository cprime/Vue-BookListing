<template>
  <div class="booklist">
    <h1>{{ title }}</h1>
    <ul>
      <book-item v-for="book in books" :key="book.title" :book="book" />
    </ul>
  </div>
</template>

<script>
import BookItem from "./BookItem";

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
  components: {
    BookItem
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
