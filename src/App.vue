<template>
  <div id="app">
    <h1>Task Manager</h1>
    <ItemForm @add-item="handleAddItem" />
    <ItemList
      :items="items"
      @delete-item="handleDeleteItem"
      @toggle-item="handleToggleItem"
    />
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
        { id: 1, name: "Learn Vue 3", done: false },
        { id: 2, name: "Build Task Manager", done: false },
        { id: 3, name: "Commit to Git", done: false },
      ],
      nextId: 4,
    };
  },
  methods: {
    handleAddItem(newItem) {
      this.items.push({ id: this.nextId++, name: newItem.name, done: false });
    },
    handleDeleteItem(id) {
      this.items = this.items.filter(item => item.id !== id);
    },
    handleToggleItem(id) {
      const item = this.items.find(item => item.id === id);
      if (item) item.done = !item.done;
    },
  },
};
</script>

<style scoped>
#app {
  display: flex;
  flex-direction: column;
  align-items: center;
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  background-color: #e0f2ff;
  min-height: 100vh;
  padding: 40px 20px;
}

#app h1 {
  color: #0369a1; 
  margin-bottom: 24px;
  font-size: 2rem;
  text-shadow: 0 1px 2px rgba(0,0,0,0.1);
}
</style>