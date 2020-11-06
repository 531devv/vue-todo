<template>
    <div v-bind:class="{completed: item.completed}">
      <button v-if=(!item.completed) @click="removeItem(item.id)">Usuń</button>
      <h2>{{ item.title }}</h2>
    </div>
</template>

<script>
export default {
    props: ['item'],
    methods: {
        removeItem(id) {
            this.$emit('removeClicked', id);
        }
    }
}
</script>