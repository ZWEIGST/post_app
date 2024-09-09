<template>
    <form  @submit.prevent>
      <h4>Создание поста</h4>
      <input 
      v-model="post.title"
      @input="inputTitle"
      class="input" 
      type="text" 
      placeholder="Название">
      <input 
      v-bind:value="post.body"
      @input="post.body = $event.target.value"
      class="input" 
      type="text" 
      placeholder="Описание">
      <button class="btn" @click="createPost">Опубликовать пост</button>
    </form>
</template>

<script>
    export default {
        data() {
          return {
            post: {
              title: '',
              body: '',
            },
            posts: [],
          };
        },
        methods: {
         createPost() {
           this.post.id = Date.now();
           this.$emit('create', this.post)
           this.post = {
           title:'',
           body:''
           }
          
        },
         inputTitle(event) {
         this.post.title = event.target.value;
         },
  },
  };
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