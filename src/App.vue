<template>
  <div>
    <div class="post" v-for="post in posts">
      <div><strong>Название</strong> {{ post.title }}</div>
      <div><strong>Description</strong> {{ post.body }}</div>
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
      ]
    }
  },
  methods: {

  }
}
</script>
<style>
* {
  margin: 0;
  padding: 0;
  border-sizing: border-box;
}

.post {
  padding: 15px 0px 15px 0px;
  border: 1px solid rgb(184, 132, 184);
  margin-top: 15px;
}
</style>