<template>
  <div id="app">
    <button @click="toggleView" class="toggle-button">
      {{ isTableView ? 'Show Card View' : 'Show Table View' }}
    </button>
    <div v-if="isTableView">
      <book-table />
    </div>
    <div v-else>
      <book-list></book-list>
    </div>
  </div>
</template>

<script>
import { books } from './bookdata' // Import the dataset
import BookList from '@/components/BookList.vue'
import BookTable from '@/components/BookTable.vue'

export default {
  name: 'App',
  components: {
    BookList,
    BookTable,
  },
  data() {
    return {
      isTableView: true, // Toggle state
      books, // Dataset
    }
  },
  methods: {
    toggleView() {
      this.isTableView = !this.isTableView
    },
  },
}
</script>

<style>
#app {
  text-align: center;
  margin: 20px;
}

.toggle-button {
  background-color: #007bff;
  color: white;
  border: none;
  padding: 10px 20px;
  margin-bottom: 20px;
  border-radius: 5px;
  cursor: pointer;
}

.toggle-button:hover {
  background-color: #0056b3;
}

.card-container {
  display: flex;
  flex-wrap: wrap;
  gap: 16px;
  justify-content: center;
  padding: 16px;
}
</style>
