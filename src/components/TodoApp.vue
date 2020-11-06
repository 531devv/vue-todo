<template>
  <div>
    <input type="text" placerholder="todo" v-model="newItem" />
    <button @click="addItem">Dodaj</button>
    <TodoItem v-bind:item="item" v-for="item in items" v-bind:key="item.id" @removeClicked = "removeItem" />
  </div>
</template>

<script>

import TodoItem from './TodoItem.vue';
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
      TodoItem
  },
  methods: {
    removeItem(id) {
      const index = this.items.findIndex(el => el.id === id);
      this.items[index].completed = true;
    },
    addItem() {
      this.items.push({
        title: this.newItem,
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
