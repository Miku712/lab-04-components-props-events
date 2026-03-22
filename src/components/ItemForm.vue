<template>
  <div class="item-form">
    <h2>Add Item</h2>
    <input
      type="text"
      v-model="newItem"
      placeholder="Enter item name"
    />
    <button @click="addItem">Add</button>
    <p v-if="error">{{ error }}</p>
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
.item-form {
  background-color: #e0f2ff;
  padding: 20px;
  border-radius: 12px;
  width: 100%;
  max-width: 400px;
  margin-bottom: 20px;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.08);
}

.item-form h2 {
  margin-bottom: 12px;
  font-size: 1.5rem;
  color: #0369a1; 
}

.item-form input {
  width: calc(100% - 16px);
  padding: 10px;
  margin-bottom: 12px;
  border: 1px solid #90cdf4;
  border-radius: 8px;
  font-size: 1rem;
  outline: none;
  transition: border 0.2s;
}

.item-form input:focus {
  border-color: #0284c7;
}

.item-form button {
  padding: 10px 18px;
  background-color: #0284c7; 
  color: white;
  border: none;
  border-radius: 8px;
  cursor: pointer;
  font-weight: 600;
  box-shadow: 0 2px 6px rgba(0,0,0,0.15);
  transition: all 0.2s ease;
}

.item-form button:hover {
  background-color: #0369a1;
  transform: translateY(-2px);
  box-shadow: 0 4px 10px rgba(0,0,0,0.2);
}

.item-form p {
  color: #e53935;
  margin-top: 5px;
  font-size: 0.9rem;
}
</style>