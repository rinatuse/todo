<script setup>
import { ref } from "vue";
const props = defineProps({
  todoItem: Object,
  todoStr: String,
});

const emit = defineEmits(["deleteElement", "hello"]);

function onDelete() {
  emit("deleteElement", props.todoItem.id);
}

function onHello() {
  emit("hello");
}

const isEditing = ref(false);

function editText() {
  isEditing.value = true;
}
</script>

<template>
  <div>
    <h1>Id:{{ props.todoItem.id }}</h1>
    <h3 @click="editText">Title:{{ props.todoItem.title }}</h3>
    <p>{{ props.todoStr }}</p>
    <input type="text" />
    <form>
      <input type="checkbox" />
      <label>Done</label>
    </form>
    <button @click="onDelete">Удалить</button>
    <button @click="onHello">hello</button>
  </div>
</template>
