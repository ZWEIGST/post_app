<template>
    <form  @submit.prevent>
      <h4>Создание поста</h4>
      <input 
      v-bind:value="title"
      @input="inputTitle"
      class="input" 
      type="text" 
      placeholder="Название">
      <input 
      v-bind:value="body"
      @input="body = $event.target.value"
      class="input" 
      type="text" 
      placeholder="Описание">
      <button class="btn" @click="createPost">Опубликовать пост</button>
    </form>
</template>

<script>
    export default {
        
    }
</script>

<style lang="scss" scoped>
form {
  display: flex;
  flex-direction: column;
}
.btn {
  margin-top: 15px;
  align-self: flex-end;
  padding: 10px 15px;
  background: none;
  color:rgb(184, 132, 184);
  border: 1px solid rgb(184, 132, 184);
}
.input {
  width: 100%;
  border: 1px solid rgb(184, 132, 184);
  padding: 10px 15px;
  margin-top: 15px;
}
</style>