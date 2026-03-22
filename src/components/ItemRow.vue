<template>
  <div>
    <span>{{ item.name }}</span>
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

<style scoped></style>