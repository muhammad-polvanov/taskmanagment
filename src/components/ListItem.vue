<template>
  <li class="content-list__item">
    <div class="header-content">
      <h2 class="header-content__title">ПОНЕДЕЛЬНИК</h2>
      <p class="header-content__date">6 СЕНТЯБРЯ 2021 Г.</p>
    </div>
    <ol class="todo">
      <li class="todo-item overflow-hidden is-editing">
        <div class="todo-content w-full">
          <label class="todo__label">
            <input
              type="text"
              class="main__input w-full outline-none text-sm"
            />
          </label>
          <div class="todo-content__text text-sm"></div>
        </div>
      </li>
    </ol>
  </li>
</template>

<script>
export default {
  name: "ListItem"
};
</script>
