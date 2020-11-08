<template>
    <div class="u-mt-5 t-todo-app__input-container">
        <input class="c-input" type="text" v-model="newItem" 
        v-on:keyup.enter="addItem" />
        <button class="c-button" @click="addItem">Send</button>
    </div>
</template>

<script>
export default {
    data() {
        return {
            newItem: ''
        }
    },
    methods: {
        addItem() {
            this.$emit('onSubmit', this.newItem);
            this.newItem = '';
        }
    }
}
</script>

<style>

</style>