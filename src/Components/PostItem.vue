<template>
        <div class="post">
            <div>
              <div><strong>Название</strong> {{ post.title }}</div>
              <div><strong>Описание</strong> {{ post.body }}</div>
            </div>
            <div class="post__btns">
               <MyButton>Delete</MyButton>
            </div>
          
       </div>
</template>

<script>
import MyButton from './UI/MyButton.vue';

    export default {
        components: {MyButton},
        props: {
            post: {
                type: Object,
                required: true,
            }
        }
    }
</script>

<style lang="scss" scoped>
 .post {
  padding: 15px 10px 15px 10px;
  border: 1px solid rgb(184, 132, 184);
  margin-top: 15px;
  display: flex;
  align-items: center;
  justify-content: space-between;
}
</style>