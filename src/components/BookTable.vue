<template>
  <div class="book-list">
    <h1>Book List</h1>
    <table>
      <thead>
        <tr>
          <th>Author</th>
          <th>Title</th>
          <th>Description</th>
          <th>Image</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="book in books" :key="book.title">
          <td>{{ book.author }}</td>
          <td>{{ book.title }}</td>
          <td>{{ book.description }}</td>
          <td><img :src="book.img_url" :alt="book.title" class="book-image" /></td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
import { books } from '../bookdata'

export default {
  name: 'BookTable',
  data() {
    return {
      books, // Use the imported books dataset
    }
  },
}
</script>

<style scoped>
.book-list {
  max-width: 800px;
  margin: 0 auto;
  padding: 20px;
}

table {
  width: 100%;
  border-collapse: collapse;
  margin-top: 20px;
}

th,
td {
  text-align: left;
  border: 1px solid #ddd;
  padding: 8px;
}

th {
  background-color: #f4f4f4;
  font-weight: bold;
}

tr:nth-child(even) {
  background-color: #f9f9f9;
}

.book-image {
  width: 50px;
  height: auto;
  border-radius: 4px;
}
</style>
