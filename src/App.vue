<template>
  <div id="app">
    <LibraryComponent>
      <template v-slot>
        <div class="custom-slot-content">
          <p>Welcome to the Library! Enjoy your reading.</p>
        </div>
      </template>
    </LibraryComponent>
  </div>
</template>

<script>
import LibraryComponent from './components/LibraryComponent.vue';

export default {
  name: 'App',
  components: {
    LibraryComponent
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.custom-slot-content {
  background-color: #f8d7da;
  padding: 10px;
  border: 1px solid #f5c6cb;
  color: #721c24;
}
</style>