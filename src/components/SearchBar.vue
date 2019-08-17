<template>
    <div class="searchBarContainer">
        <input @input="onInput" @change="onInputChange" class="input is-primary" type="text" placeholder="Search here..." />
    </div>
</template>

<script>
export default {
    name: 'SearchBar',
    data(){
        return {
            textInput: ''
        };
    },
    methods: {
        onInputChange() {
            this.$emit('termChange', this.textInput);
        },
        onInput(event) {
            this.textInput = event.target.value;
        }
    }
}
</script>

<style scoped>
    .searchBarContainer,
    .searchBarContainer > input {
        width: 100%;
    }
</style>