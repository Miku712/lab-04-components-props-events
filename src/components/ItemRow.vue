<template>
  <div class="item-row">
    <span :class="{ done: item.done }">
      {{ item.name }}
    </span>
    <button @click="$emit('toggle-item', item.id)">
      {{ item.done ? "Undo" : "Done" }}
    </button>
    <button class="delete" @click="$emit('delete-item', item.id)">Delete</button>
  </div>
</template>

<script>
export default {
  name: "ItemRow",
  props: {
    item: {
      type: Object,
      required: true,
    },
  },
};
</script>

<style scoped>
.item-row {
  display: flex;
  align-items: center;
  justify-content: space-between;
  background-color: #f0f9ff;
  padding: 12px 16px;
  margin-bottom: 10px;
  border-radius: 10px;
  box-shadow: 0 2px 6px rgba(0,0,0,0.06);
  font-size: 1rem;
  transition: transform 0.15s, box-shadow 0.15s;
}

.item-row:hover {
  transform: translateY(-2px);
  box-shadow: 0 4px 12px rgba(0,0,0,0.1);
}

.item-row span.done {
  text-decoration: line-through;
  color: #90a4ae;
}

.item-row button {
  padding: 6px 14px;
  border: none;
  border-radius: 8px;
  cursor: pointer;
  font-size: 0.9rem;
  margin-left: 8px;
  font-weight: 500;
  transition: all 0.2s;
}

.item-row button:not(.delete) {
  background-color: #0284c7;
  color: white;
  box-shadow: 0 2px 6px rgba(0,0,0,0.15);
}

.item-row button:not(.delete):hover {
  background-color: #0369a1;
  transform: translateY(-1px);
  box-shadow: 0 4px 8px rgba(0,0,0,0.2);
}

.item-row button.delete {
  background-color: #f87171; 
  color: white;
  box-shadow: 0 2px 6px rgba(0,0,0,0.15);
}

.item-row button.delete:hover {
  background-color: #dc2626;
  transform: translateY(-1px);
  box-shadow: 0 4px 8px rgba(0,0,0,0.2);
}
</style>