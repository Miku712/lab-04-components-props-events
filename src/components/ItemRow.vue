<template>
  <div style="display: flex; align-items: center; gap: 10px;">
    <span :style="{ textDecoration: item.done ? 'line-through' : 'none' }">
      {{ item.name }}
    </span>
    <button @click="$emit('toggle-item', item.id)">
      {{ item.done ? "Undo" : "Done" }}
    </button>
    <button @click="$emit('delete-item', item.id)">Delete</button>
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
button {
  cursor: pointer;
}
</style>