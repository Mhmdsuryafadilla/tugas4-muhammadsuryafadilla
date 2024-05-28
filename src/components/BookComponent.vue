<template>
    <div class="book" @click="selectBook">
      <p>{{ title }}</p>
      <button v-if="title === 'Book A'" @click.stop="triggerWarning">Emit</button>
    </div>
  </template>
  
  <script>
  export default {
    name: 'BookComponent',
    props: {
      title: String
    },
    methods: {
      selectBook() {
        this.$emit('bookSelected', this.title);
      },
      triggerWarning() {
        this.$emit('warningTriggered', 'Warning: Special attention needed for Book A!');
      }
    }
  }
  </script>
  
  <style scoped>
  .book {
    background-color: #f8f9fa;
    padding: 10px;
    margin: 5px;
    border: 1px solid #ddd;
    cursor: pointer;
    text-align: center;
  }
  .book:hover {
    background-color: #e9ecef;
  }
  button {
    margin-top: 10px;
    padding: 5px 10px;
    background-color: #ffc107;
    border: none;
    cursor: pointer;
  }
  button:hover {
    background-color: #e0a800;
  }
  </style>