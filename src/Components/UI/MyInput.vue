<template>
    <input :value="modelValue" @input="updateInput" type="text" class="input">

</template>

<script>
    export default {
        name: 'MyInput',
        props: {
            value: [String, Number]
        },
        methods: {
            updateInput(event) {
                this.$emit('update:value', event.target.value);
            },
        },
    }
</script>

<style lang="scss" scoped>
.input {
  width: 100%;
  border: 1px solid rgb(184, 132, 184);
  padding: 10px 15px;
  margin-top: 15px;
}
</style>