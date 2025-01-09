<template>
  <div class="app">
    <postForm
    @create="createPost"
    />
    <postList 
    v-bind:posts="posts"
    @remove="removePost"
    />
  </div>
</template>
<script>
import postForm  from "@/Components/postForm";
import postList  from "./Components/postList";
export default {
  components: {
    postList, postForm,
  },
  data() {
    return {
      posts: [
        {id: 1, title: 'Анатомическая амуниция 1', body: 'Описание поста 1'},
        {id: 2, title: 'Анатомическая амуниция 2', body: 'Описание поста 2'},
        {id: 3, title: 'Анатомическая амуниция 3', body: 'Описание поста 3'},
        {id: 4, title: 'Анатомическая амуниция 4', body: 'Описание поста 4'},
      ],
   }
  },
      methods: {
      createPost(post) {
      this.posts.push(post);
    },
    removePost(post) {
      this.posts = this.posts.filter(p => p.id !== post.id)
    }
  }
}
</script>
<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
.app {
  padding: 20px;
}
</style>