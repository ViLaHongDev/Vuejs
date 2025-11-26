<script setup>
    import { ref } from 'vue';

    const title = ref('')
    const content = ref('')
    const author = ref('')

    const emit = defineEmits(['submit-post']);

    function handleSubmit() {

        if(title.value && content.value && author.value){
            const newPost = {
                title : title.value,
                content : content.value,
                author : author.value
            }
            // Gửi dữ liệu lên parent thông qua emit
            emit('submit-post',newPost);

             // reset form
            title.value = ''
            content.value = ''
            author.value = ''

        }

        
    }

</script>
<template>
    <form>
        <div>
            <label for="title">Tiêu đề</label>
            <input type="text" v-model="title" placeholder="Nhập tiêu đề....">
        </div>
        <div>
            <label for="content">Nội dung</label>
            <input type="text" v-model="content" placeholder="Nhập nội dung....">
        </div>
        <div>
            <label for="author">Tác giả</label>
            <input type="text"v-model="author" placeholder="Nhập tác giả">
        </div>
        <button type="button" @click="handleSubmit">ĐĂNG BÀI</button>
    </form>
</template>
<style scoped>

</style>