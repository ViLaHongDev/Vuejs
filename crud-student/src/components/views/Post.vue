<script setup>
    import { ref, watch } from 'vue';

    const mssv = ref('');
    const name = ref('');
    const age = ref('')

    const props = defineProps({
        editingStudent : {
            type : Object,
            default: null,
        },
    }); 

    const isEditing = ref(false);

    watch(
        () => props.editingStudent,
        (newValue) => {
            if(newValue){
                mssv.value = newValue.mssv;
                name.value = newValue.name;
                age.value = newValue.age;
                isEditing.value = true;
            }else{
                mssv.value = "";
                name.value = "";
                age.value = "";
                isEditing.value = false;
            }
        }
    );

    const emit = defineEmits(['add-student','update-student']);

    const handleSubmit = () => {
        const student = {
            mssv : mssv.value,
            name : name.value,
            age : age.value
        }

        emit('add-student',student);

        resetForm();

        isEditing.value = false;
    }

    const resetForm = () => {
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
