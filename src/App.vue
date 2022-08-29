<template> <!--Пишется разметка компонента-->
<div class="app">
  <post-form @create="createPost"/>
  <post-list :posts="posts" />
</div>
</template>

<script> //Описывается логика компонета

import PostList from "@/components/PostList";
import PostForm from "./components/PostForm";

export default  {
  components: {
    PostList, PostForm
  },
  data() {
    return {
      posts: [
        {id: 1, title: 'JavaScript', body: 'Описание поста JavaScript'},
        {id: 2, title: 'NodeJS', body: 'Описание поста NodeJS'},
        {id: 3, title: 'Vue', body: 'Описание поста Vue'},
        {id: 4, title: 'React', body: 'Описание поста React'},
      ],
    }
  },
  methods: { // Поле для создания функций
    createPost(post) {
      this.posts.push(post)
      }
    },
}
</script>

<style> /*флаг scoped - говорит о том, что стили будут применены только к данному компоненту и не будут доступны из вне*/
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

.app {
  padding: 15px;
}


</style>