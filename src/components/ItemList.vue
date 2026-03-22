<template>
  <div class="item-list">
    <h2>Item List</h2>
    <ItemRow
      v-for="item in items"
      :key="item.id"
      :item="item"
      @delete-item="$emit('delete-item', $event)"
      @toggle-item="$emit('toggle-item', $event)"
    />
  </div>
</template>

<script>
import ItemRow from "./ItemRow.vue";

export default {
  name: "ItemList",
  props: {
    items: {
      type: Array,
      default: () => [],
    },
  },
  components: {
    ItemRow,
  },
};
</script>

<style scoped>
.item-list {
  width: 100%;
  max-width: 500px;
}

.item-list h2 {
  margin-bottom: 16px;
  color: #0369a1;  
  font-size: 1.4rem;
}
</style>