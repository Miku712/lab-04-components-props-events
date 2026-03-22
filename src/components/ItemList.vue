<template>
  <div>
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

<style scoped></style>