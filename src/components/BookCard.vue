<script>
export default {
  name: "BookCard",
  props: {
    book: {
      type: Object,
      required: true,
    },
  },
};</script>

<template>
  <div class="book-card">
    <img :src="book.img_url" :alt="book.title" class="book-image" />
    <div class="book-details">
      <h2>{{ book.title }}</h2>
      <h3>{{ book.author }}</h3>
      <p>{{ book.description }}</p>
    </div>
  </div>
</template>

<style scoped>
.book-card {
  display: flex;
  flex-direction: column;
  align-items: center;
  border: 1px solid #ddd;
  border-radius: 8px;
  max-width: 25%;
}

.book-image {
  width: 100%;
  border-radius: 4px;
}

.book-details h2 {
  margin: 0;
  font-size: 1.2em;
}

.book-details h3 {
  margin: 8px 0;
  font-size: 1em;
  color: #555;
}

.book-details p {
  margin: 0;
  color: #333;
}
</style>
