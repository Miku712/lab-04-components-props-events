<template>
  <div>
    <h2>Add Item</h2>
    <input
      type="text"
      v-model="newItem"
      placeholder="Enter item name"
    />
    <button @click="addItem">Add</button>
    <p v-if="error" style="color: red">{{ error }}</p>
  </div>
</template>

<script>
export default {
  name: "ItemForm",
  data() {
    return {
      newItem: "",
      error: "",
    };
  },
  methods: {
    addItem() {
      if (!this.newItem.trim()) {
        this.error = "Поле не може бути порожнім";
        return;
      }
      if (this.newItem.trim().length < 3) {
        this.error = "Мінімальна довжина 3 символи";
        return;
      }

      this.$emit("add-item", { name: this.newItem.trim() });

      this.newItem = "";
      this.error = "";
    },
  },
};
</script>

<style scoped>
input {
  margin-right: 10px;
}
</style>