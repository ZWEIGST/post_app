<template>
    <div>
        <div class="post" v-for="post in posts" :key="post.id">
          <div><strong>Название</strong> {{ post.title }}</div>
          <div><strong>Описание</strong> {{ post.body }}</div>
       </div>
    </div>
</template>

<script>
    export default {
        props: {
          posts: {
            type: Array,
            require: true,
          }
        }
    }
</script>

<style scoped>
.post {
  padding: 15px 0px 15px 0px;
  border: 1px solid rgb(184, 132, 184);
  margin-top: 15px;
}
</style>