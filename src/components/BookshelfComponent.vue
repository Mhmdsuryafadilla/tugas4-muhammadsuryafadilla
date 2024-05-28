<template>
  <div class="bookshelf">
    <p>Bookshelf</p>
    <div class="books">
      <BookComponent v-for="book in books" :key="book" :title="book" @bookSelected="handleBookSelected" @warningTriggered="handleWarningTriggered"/>
    </div>
  </div>
</template>

<script>
import BookComponent from './BookComponent.vue';

export default {
  name: 'BookshelfComponent',
  components: {
    BookComponent
  },
  props: {
    books: Array
  },
  methods: {
    handleBookSelected(book) {
      this.$emit('bookFromShelf', book);
    },
    handleWarningTriggered(warning) {
      this.$emit('warningFromShelf', warning);
    }
  }
}
</script>

<style scoped>
.bookshelf {
  background-color: #f1f3f5;
  padding: 20px;
  margin: 10px;
  border: 1px solid #ccc;
}
.books {
  display: flex;
  flex-wrap: wrap;
}
</style>