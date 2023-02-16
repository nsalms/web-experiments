<script setup lang="ts">

  interface IProduct {
    id?: number,
    title: string,
    price: number
  }

  defineProps<IProduct>();
</script>

<template>
  <div>
    <span class="id">{{ id }}</span>
    <h3>{{ title }}</h3>
    <span>{{ price }}$</span>
  </div>
</template>

<style scoped>
  div {
    border-radius: 8px;
    background-color: #1a1a1a;

    padding: 1em;
    min-width: 12rem;
  }

  h3 {
    margin: 0;
  }

  .id {
    opacity: 0.5;
  }
</style>