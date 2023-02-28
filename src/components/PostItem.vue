<template>
  <div class="post">
    <div><strong>Name:</strong> {{ post.title }}</div>
    <div><strong>Description:</strong> {{ post.body }}</div>
  </div>
</template>

<script>
export default {
  props: {
    post: {
      type: Object,
      required: true,
    }
  },
  name: "PostItem"
}
</script>

<style scoped>

</style>