<template>
    <div class="library">
      <h1>Library</h1>
      <div v-if="warningMessage" class="warning">
        {{ warningMessage }}
      </div>
      <BookshelfComponent :books="bookList" @bookFromShelf="displayBookDetails" @warningFromShelf="displayWarning"/>
      <div class="slot-container">
        <slot></slot>
      </div>
      <p v-if="selectedBook">Selected Book: {{ selectedBook }}</p>
    </div>
  </template>
  
  <script>
  import BookshelfComponent from './BookshelfComponent.vue';
  
  export default {
    name: 'LibraryComponent',
    components: {
      BookshelfComponent
    },
    data() {
      return {
        bookList: ['Book A', 'Book B', 'Book C', 'Book D'],
        selectedBook: null,
        warningMessage: ''
      };
    },
    methods: {
      displayBookDetails(book) {
        this.selectedBook = book;
        this.warningMessage = '';
      },
      displayWarning(warning) {
        this.warningMessage = warning;
      }
    }
  }
  </script>
  
  <style scoped>
  .library {
    background-color: #e2e6ea;
    padding: 30px;
    border: 1px solid #bbb;
    text-align: center;
  }
  .slot-container {
    margin-top: 20px;
    padding: 15px;
    border: 1px dashed #888;
  }
  .warning {
    background-color: #f8d7da;
    color: #721c24;
    padding: 10px;
    border: 1px solid #f5c6cb;
    margin-bottom: 20px;
  }
  </style>