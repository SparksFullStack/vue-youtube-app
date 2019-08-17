<template>
    <div>
        <input @input="onInput" />
        <p>{{ textInput }}</p>
    </div>
</template>

<script>
export default {
    name: 'SearchBar',
    data() {
        return {
            textInput: ''
        }
    },
    methods: {
        onInput(event) {
            this.textInput = event.target.value;
        }
    }
}
</script>

<style scoped>

</style>