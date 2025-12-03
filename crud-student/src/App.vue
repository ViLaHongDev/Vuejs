<script setup>
    import { ref } from 'vue';
    import Post from './components/views/Post.vue';
    import List from './components/views/List.vue';

    const students = ref([]);
    const editingStudent = ref(null);
    const editingIndex = ref(null);

    const addStudent = (newStudent) => {
        students.value.push(newStudent);
    };

    const deleteStudent = (index) => {
        students.value.splice(index,1);
    };

    const startEdit = (student,index) => {
        editingStudent.value = {...student};
        editingIndex.value = index;
    }
</script>

<template>
    <Post @add-student="addStudent"
          :editing-student="editingStudent"/>
    <List :list="students" 
          @delete-student="deleteStudent"
          @edit-student="startEdit"/>
</template>

<style scoped>

</style>
