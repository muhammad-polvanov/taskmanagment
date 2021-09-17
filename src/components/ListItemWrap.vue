<template>
  <ul class="content-list glider">
    <ListItem />
  </ul>
</template>

<script>
import ListItem from "./ListItem.vue";
export default {
  name: "ListItemWrap",
  components: {
    ListItem
  }
};
</script>
<style scoped></style>
