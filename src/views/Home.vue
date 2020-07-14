<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <h1>Welcome to Your Vue.js App</h1>
    <div>{{ name }}</div>
    <div>
      <button @click="onClick">Click me</button>
      <button @click="addItem">Add to Collection</button>
    </div>
    <div v-for="i in coll" :key="i.name">
      {{ i.name }}
    </div>
  </div>
</template>
<script>
import { ref, reactive } from "vue";

export default {
  setup() {
    const name = ref("Shawn");
    const coll = reactive([]);

    function onClick() {
      name.value = name.value + "+";
    }

    function addItem() {
      coll.push({ name: "Hello World" });
    }

    return {
      name,
      onClick,
      coll,
      addItem
    }
  }
}
</script>
