<template>
  <div class="o-container">
    <div class="o-row">
      <div class="o-col t-todo-app__col">
        <div class="t-todo-app__container">
          <div class="o-col t-todo-app__header">
            <h1>Todo's</h1>
          </div>
          <div class="o-col t-todo-app__main-container">
            <div class="t-todo-app__todo-item-box">
              <TodoItem v-bind:item="item" v-for="item in items" v-bind:key="item.id" @doneClicked = "setItemDone" @removeClicked = "removeItem"/>
            </div>
            <TodoInput @onSubmit="addItem" />
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>

import TodoItem from './TodoItem.vue';
import TodoInput from './TodoInput.vue';
export default {
  data() {
    return {
      newItem: '',
      items: [
        {id: 1, title: 'Zrobić zakupy', completed: false},
        {id: 2, title: 'Zrobić cos', completed: true}
      ]
    }
  },
  components: {
      TodoItem,
      TodoInput
  },
  methods: {
    removeItem(id) {
      const index = this.items.findIndex(el => el.id === id);
      this.items.splice(index, 1);
    },
    setItemDone(id) {
      const index = this.items.findIndex(el => el.id === id);
      if(!this.items[index].completed) {
        this.items[index].completed = true;
      } else {
        this.items[index].completed = false;
      }
    },
    addItem(newItem) {
      this.items.push({
        title: newItem,
        completed: false,
        id: Math.random()
      })
    }
  },
}
</script>

<style>
.completed {
  text-decoration: line-through;
  color: rgb(70, 70, 70);
}
</style>
