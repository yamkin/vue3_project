<template>
  <form class="form" @submit.prevent>
    <h3 class="title">Создание поста</h3>
    <input v-model="post.title" class="input" type="text" placeholder="Название">
    <input v-model="post.body" class="input" type="text" placeholder="Описание">
    <button @click="createPost" class="btn">Создать</button>
  </form>
</template>

<script>
export default {
  data() {
    return {
      post: {
        title: '',
        body: ""
      }
    }
  },
  methods: { // Поле для создания функций
    createPost() {
      this.post.id = Date.now()
      this.$emit('create', this.post)
      this.post = {
        title: '',
        body: ''
      }
    },
  }
}
</script>

<style>
.form {
  display: flex;
  flex-direction: column;
}
.title{
  margin-bottom: 15px;
}

.btn{
  margin-top: 15px;
  align-self: flex-end;
  padding: 10px 35px;
  background-color: #326ee2;
  border: transparent;
  border-radius: 25px;
  color: #fff;
  cursor: pointer;
}

.input{
  width: 100%;
  padding: 10px 15px;
  border: 2px solid #326ee2;
  margin-bottom: 5px;
  outline: none;
}
</style>