<script setup lang="ts">
import ListItem from "./components/ListItem.vue";
import { ref } from "vue";

let items = ref([
  { id: 1, title: "Buy bread", isChecked: false },
  { id: 2, title: "Buy sausage", isChecked: false },
  { id: 3, title: "Buy butter", isChecked: false },
  { id: 4, title: "Buy milk", isChecked: false },
]);

let str = ref("Moscow");

function removeElement(id) {
  items.value = items.value.filter((item) => item.id !== id);
}

function showAlert() {
  alert("Hello");
}
</script>

<template>
  <div v-for="item in items" :key="item.id">
    <ListItem
      :todoItem="item"
      :todoStr="str"
      @deleteElement="removeElement"
      @hello="showAlert"
    />
  </div>
</template>

<style scoped></style>
