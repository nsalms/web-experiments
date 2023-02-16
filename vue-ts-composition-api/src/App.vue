<script setup lang="ts">
import {reactive, ref} from "vue";
  import ProductCard from "./components/ProductCard.vue";
  import AddingForm from "./components/AddingForm.vue";
  import {IProduct} from "./useProduct";

  let msg = ref("Hello ts");

  const data = reactive<IProduct[]>([
    {
      id: 1,
      title: "Sweater",
      price: 99,
    },
    {
      id: 0,
      title: "Boots",
      price: 29
    }
  ]);

  function add(payload: IProduct) {
    payload.id = (data[0].id || 0) + 1
    data.unshift(payload)
  }


</script>

<template>
  <div class="container">
    <AddingForm @submit="add"></AddingForm>
    <div class="list">
      <ProductCard v-for="item in data" :id="item.id" :title="item.title" :price="item.price" :key="item.id"></ProductCard>
    </div>
  </div>
</template>

<style scoped>

.list {
  display: flex;
  flex-direction: column;
  gap: 0.5rem;

  justify-content: center;
}
</style>
