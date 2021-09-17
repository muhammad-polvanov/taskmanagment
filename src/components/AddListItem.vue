<template>
  <li
    class="todo-item overflow-hidden"
    :class="{
      'is-editing': isVisible === true,
      'is-completed': isCompleted
    }"
    @click="completed"
  >
    <div class="todo-content w-full">
      <label class="todo__label">
        <input
          v-model="editInput"
          v-if="isVisible"
          type="text"
          class="main__input w-full outline-none text-sm"
        />
      </label>
      <div class="todo-content__text text-sm">
        {{ propValue.name }}
      </div>
    </div>
    <div class="todo-buttons absolute top-0 right-2 opacity-0">
      <button class="todo-buttons__button todo-buttons__button_delete text-sm">
        <delete-button />
      </button>
      <button
        @click="editTodo"
        class="todo-buttons__button todo-buttons__button_edit text-sm"
      >
        <edit-button />
      </button>
    </div>
  </li>
</template>

<script>
import EditButton from "./Buttons/EditButton.vue";
import DeleteButton from "./Buttons/DeleteButton.vue";
export default {
  name: "ListItem",
  components: {
    DeleteButton,
    EditButton
  },
  props: {
    todoValue: Object
  },
  data() {
    return {
      isVisible: false,
      isCompleted: false,
      editInput: "",
      propValue: this.$props.todoValue
    };
  },
  methods: {
    editTodo() {
      this.isVisible = !this.isVisible;
      this.$emit("editTodo");
      this.editInput = this.propValue.name;
    },
    completed() {
      return (this.isCompleted = !this.isCompleted);
    }
  }
};
</script>
