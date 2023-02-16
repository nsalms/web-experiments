<script setup lang="ts">
import {reactive, toRefs} from "vue";
import {IProduct} from "../useProduct";

const emit = defineEmits({
  submit(payload: IProduct) {
    return payload
  }
})

const form = reactive<IProduct>({
  title: "",
  price: 0
})

function submitForm() {
  emit("submit", {...form});
}
</script>

<template>
  <form @submit.prevent="submitForm">
    <input v-model.trim="form.title" type="text" placeholder="Title">
    <input v-model="form.price" type="number" placeholder="Price">
    <button type="submit">Add</button>
  </form>
</template>

<style scoped>
  form {
    width: 100%;
    display: flex;
    flex-direction: column;
    gap: 0.5rem;
    margin: 2em auto;
  }
</style>