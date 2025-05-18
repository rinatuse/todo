<script setup lang="ts">
import { ref } from "vue";
const firstInput = ref(22);
const secondInput = ref("");
function onChangeInput(event) {
  console.log(event.target.value);
  console.log(firstInput.value);

  firstInput.value = event.target.value;
}
</script>

<template>
  <div>
    <form @submit.prevent="onChangeInput">
      <input type="text" :value="firstInput" @change="onChangeInput($event)" />
      <input v-model="secondInput" />
      <button>Добавить</button>
    </form>
  </div>
</template>

<style scoped></style>
