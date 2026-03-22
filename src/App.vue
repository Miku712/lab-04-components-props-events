<template>
  <div id="app">
    <h1>Task Manager</h1>
    <ItemForm @add-item="handleAddItem" />
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
        { id: 1, name: "Learn Vue 3" },
        { id: 2, name: "Build Task Manager" },
        { id: 3, name: "Commit to Git" },
      ],
      nextId: 4, 
    };
  },
  methods: {
    handleAddItem(newItem) {
      this.items.push({ id: this.nextId++, name: newItem.name });
    },
  },
};
</script>