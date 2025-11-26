<script setup>
  import { ref } from 'vue';
  import PostForm from './views/PostForm.vue';

    const posts = ref([])

    // Hàm nhận dữ liệu từ child
    function addPost(newPost) {
      posts.value.push(newPost)
    }

</script>

<template>
    <h1>Trang đăng bài</h1>
    <PostForm @submit-post="addPost"></PostForm>
    <h2>Danh sách bài viết</h2>
    <ul>
      <li v-for="(post,index) in posts" :key="index">
        <h3>{{ post.title }}</h3>
        <p>{{ post.content }}</p>
        <p>{{ post.author }}</p>
      </li>
      
    </ul>
</template>

<style scoped>

</style>

