<template>
    <div class="book-list">
      <h1>Book List</h1>
      <div class="card-container">
        <BookCard v-for="book in books" :key="book.title" :book="book" />
      </div>
    </div>
  </template>
  
  <script setup>
  import { books } from "../bookdata";
  import BookCard from "../components/BookCard.vue";
  </script>
  
  <style scoped>
  .book-list {
    display: flex;
    flex-direction: column;
  }

  .card-container {
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
  }
  </style>
  