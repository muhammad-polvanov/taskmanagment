<template>
  <Header />
  <main class="main">
    <div class="main-wrapper">
      <div class="left-side border-r flex items-center justify-start flex-col">
        <next-icon />
        <next-page-ico />
      </div>
      <div class="content overflow-hidden">
        <div class="content-wrap glider-contain multiple">
          <ul class="content-list glider">
            <li class="content-list__item">
              <div class="header-content">
                <h2 class="header-content__title">ПОНЕДЕЛЬНИК</h2>
                <p class="header-content__date">6 СЕНТЯБРЯ 2021 Г.</p>
              </div>
              <ol class="todo">
                <add-list-item
                  v-for="(content, index) in todoContent"
                  :key="index"
                  :todoValue="content"
                  @editTodo="editTodo(content)"
                />
                <li class="todo-item overflow-hidden is-editing">
                  <div class="todo-content w-full">
                    <label class="todo__label">
                      <input
                        v-model="todoText"
                        @keyup.enter="addTodo(todoText)"
                        type="text"
                        class="main__input w-full outline-none text-sm"
                      />
                    </label>
                    <div class="todo-content__text text-sm"></div>
                  </div>
                </li>
              </ol>
            </li>
          </ul>
        </div>
      </div>
      <div class="right-side border-l flex items-center justify-start flex-col">
        <prev-icon />
        <prev-page-ico />
      </div>
    </div>
  </main>
</template>

<script>
import Header from "./components/Header.vue";
// import ListItemWrap from "./components/ListItemWrap.vue";
import NextIcon from "./components/Icons/NextIcon.vue";
import NextPageIco from "./components/Icons/NextPageIco.vue";
import PrevIcon from "./components/Icons/PrevIcon.vue";
import PrevPageIco from "./components/Icons/PrevPageIco.vue";
import AddListItem from "./components/AddListItem.vue";
import "boxicons";
import { state } from "./data";

export default {
  name: "App",
  components: {
    Header,
    // ListItemWrap,
    NextIcon,
    NextPageIco,
    PrevIcon,
    PrevPageIco,
    AddListItem
  },
  data() {
    return {
      todoText: "",
      todoContent: [],
      data: state.data
    };
  },
  methods: {
    addTodo(index) {
      if (this.todoText.length) {
        const newTodo = {
          name: index,
          completed: false
        };
        this.todoContent.push(newTodo);
        this.todoText = "";
      }
    },
    editTodo(index) {
      console.log(index);
    }
  }
};
</script>

<style src="./assets/css/tailwind.css"></style>
<style src="./assets/css/main.css"></style>
<style src="./assets/css/glide.min.css"></style>
