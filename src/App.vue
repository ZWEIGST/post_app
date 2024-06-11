<template>
  <div class="app">
    <postForm/>
    <postList/>
  </div>
</template>
<script>
import postForm  from "@/Components/postForm";
import postList  from "./Components/postList";
export default {
  components {
    postList, postForm,
  },
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
</style>