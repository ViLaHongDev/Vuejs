<script setup>
    import { ref } from 'vue';
    import Post from './components/views/Post.vue';
    import List from './components/views/List.vue';

    const students = ref([]);

    const addStudent = (newStudent) => {
        students.value.push(newStudent);
    };

    const deleteStudent = (index) => {
        students.value.splice(index,1);
    };

</script>

<template>
    <Post @add-student="addStudent"/>
    <List :list="students" 
          @delete-student="deleteStudent"/>
</template>

<style scoped>

</style>
