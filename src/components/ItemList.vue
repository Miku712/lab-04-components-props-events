<template>
  <div>
    <h2>Item List</h2>
  </div>
</template>

<script>
export default {
  name: "ItemList",
  props: {
    items: {
      type: Array,
      default: () => [],
    },
  },
};
</script>

<style scoped></style>