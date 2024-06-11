<template>
  <div class="app">
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
    <div class="post" v-for="post in posts" :key="post.id">
      <div><strong>Название</strong> {{ post.title }}</div>
      <div><strong>Описание</strong> {{ post.body }}</div>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      posts: [
        {id: 1, title: 'Анатомическая амуниция 1', body: 'Описание поста 1'},
        {id: 2, title: 'Анатомическая амуниция 2', body: 'Описание поста 2'},
        {id: 3, title: 'Анатомическая амуниция 3', body: 'Описание поста 3'},
      ],
      title: '',
      body: '',
    }
  },
  methods: {
   createPost() {
     const newPost = {
      id: Date.now(),
      title: this.title,
      body: this.body,
     }
     this.posts.push(newPost);
     this.title = '';
     this.body = '';
   },
   inputTitle(event) {
     this.title = event.target.value;
   }
  },
}
</script>
<style>
* {
  margin: 0;
  padding: 0;
  border-sizing: border-box;
}
.app {
  padding: 20px;
}
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
.post {
  padding: 15px 0px 15px 0px;
  border: 1px solid rgb(184, 132, 184);
  margin-top: 15px;
}
.input {
  width: 100%;
  border: 1px solid rgb(184, 132, 184);
  padding: 10px 15px;
  margin-top: 15px;
}
</style>