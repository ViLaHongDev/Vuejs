<script setup>
    import { ref } from 'vue';

    const mssv = ref('');
    const name = ref('');
    const age = ref('')

    const emit = defineEmits(['add-student']);


    const handleSubmit = () => {
        const student = {
            mssv : mssv.value,
            name : name.value,
            age : age.value
        }

        // 
        emit('add-student',student);

        //clear form
        mssv.value = "";
        name.value = "";
        age.value = "";
    }
    
</script>

<template>
    <form>
        <label for="">mssv</label> <br>
        <input type="text" name="" id="" v-model="mssv"> <br>
        <label for="">name</label> <br>
        <input type="text" name="" id="" v-model="name"> <br>
        <label for="">age</label> <br>
        <input type="text" name="" id="" v-model="age"> <br>
        <button @click="handleSubmit" type="button">Add</button>
    </form>
</template>

<style scoped>

</style>
