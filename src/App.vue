<template>
  <div id="app">
    <h1>Task Manager</h1>
    <ItemForm />
    <ItemList :items="items" />
  </div>
</template>

<script>
import ItemForm from "./components/ItemForm.vue";
import ItemList from "./components/ItemList.vue";

export default {
  name: "App",
  components: {
    ItemForm,
    ItemList,
  },
  data() {
    return {
      items: [],
    };
  },
};
</script>

<style>
</style>