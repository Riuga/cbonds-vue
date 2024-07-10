<template>
  <h3>30 категорий данных с Росстата</h3>
  <ul>
    <li v-for="category in categories" :class="[category.shadow ? 'shadow' : '', category.active ? 'active' : '']">{{
      category.text }}</li>
  </ul>
</template>

<script setup>
import { categories } from "@/data/categories.js";

</script>

<style scoped>
ul {
  padding: 0;
  list-style-type: none;
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  gap: 1rem;
}

li {
  border: 1px solid var(--border-lgrey);
  border-radius: 20px;
  text-align: center;
  padding: 0.5em;
  cursor: pointer;
}

.active {
  background-color: var(--bg-orange);
  color: var(--text-white);
}

.shadow {
  box-shadow: 0 3px 10px var(--border-lgrey);
}
</style>