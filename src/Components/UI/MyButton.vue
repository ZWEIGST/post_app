<template>
    <button class="btn">
    <slot></slot>
    </button>
</template>

<script>
    export default {
        
    }
</script>

<style lang="scss" scoped>
.btn {
  margin-top: 15px;
  align-self: flex-end;
  padding: 10px 15px;
  background: none;
  color:rgb(184, 132, 184);
  border: 1px solid rgb(184, 132, 184);
}
</style>