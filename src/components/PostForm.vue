<template>
  <form @submit.prevent>
    <h2>Create Post</h2>
    <input
        v-model="post.title"
        class="input"
        type="text"
        placeholder="name of post">
    <input
        v-model="post.body"
        class="input"
        type="text"
        placeholder="description">
    <button
        class="button-input"
        @click="createPost"
    >Create Post
    </button>
  </form>
</template>

<script>
export default {
  name: "PostForm",
  data() {
    return {
      post: {
        title: '',
        body: ''
      }
    }
  },
  methods: {
    createPost() {
      this.post.id = Date.now()
      this.$emit('create', this.post)
      this.post = {
        title: '',
        body: ''
      }
    }
  }
}
</script>

<style scoped>
.input {
  width: 100%;
  border: 1px solid teal;
  padding: 18px 15px;
  margin-top: 15px;
}

form {
  display: flex;
  flex-direction: column;
}

.button-input {
  align-self: flex-end;
  margin-top: 15px;
  padding: 10px 15px;
  background: none;
  color: teal;
  border: 1px solid teal;
}
</style>