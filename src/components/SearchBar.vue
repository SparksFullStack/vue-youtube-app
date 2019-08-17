<template>
    <div>
        <input @input="onInput" @change="onInputChange"/>
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

</style>