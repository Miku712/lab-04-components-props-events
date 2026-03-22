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
      items: [
        { id: 1, name: "Read about Vue 3" },
        { id: 2, name: "Create Task Manager" },
        { id: 3, name: "Commit to Git" },
      ],
    };
  },
};
</script>

<style>
</style>