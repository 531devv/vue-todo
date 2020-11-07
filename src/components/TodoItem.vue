<template>
    <div class="t-todo-app__text-box" v-bind:class="{completed: item.completed}">
      <h2 class="t-todo-app__text">{{ item.title }}</h2>
      <div class="t-todo-app__icons">
        <span class="u-done" @click="setItemDone(item.id)"></span>
        <span class="u-delete" @click="removeItem(item.id)"></span>
      </div>
    </div>
</template>

<script>
export default {
    props: ['item'],
    methods: {
        removeItem(id) {
            this.$emit('removeClicked', id);
        },
        setItemDone(id) {
            this.$emit('doneClicked', id);
        }
    }
}
</script>