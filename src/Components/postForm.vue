<template>
    <form  @submit.prevent>
      <h4>Создание поста</h4>
      <MyInput
      v-model="post.title" 
      type="text" 
      placeholder="Название"
      />
      <MyInput
      v-bind:value="post.body"
      type="text" 
      placeholder="Описание"
      />
      <MyButton 
       class="btn"
       style="align-self: flex-end;" 
       @click="createPost">
       Опубликовать пост
      </MyButton>
    </form>
</template>

<script>
import MyButton from './UI/MyButton.vue';
import MyInput from './UI/MyInput.vue';

    export default {
      comments: {
        MyButton,
        MyInput,
      },
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
</style>