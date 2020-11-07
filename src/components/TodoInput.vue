<template>
    <div>
        <input class="c-input" type="text" v-model="newItem" 
        v-on:keyup.enter="addItem" />
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