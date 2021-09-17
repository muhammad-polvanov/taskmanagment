<template>
  <div class="todo-buttons absolute top-0 right-2 opacity-0">
    <DeleteButton />
    <EditButton />
  </div>
</template>

<script>
import DeleteButton from "./DeleteButton.vue";
import EditButton from "./EditButton.vue";
export default {
  name: "ButtonsGroup",
  components: {
    DeleteButton,
    EditButton
  }
};
</script>
<style scoped></style>
