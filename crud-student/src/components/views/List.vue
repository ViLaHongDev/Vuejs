<script setup>
    defineProps({
        list: {
            type: Array,
            required: true,
        },
    });

    const emit = defineEmits(['delete-student']);

    const handleDelete = (index) => {
        emit('delete-student',index);
    };

</script>

<template>
    <div>
    <h3>Danh sách sinh viên</h3>
    <table border="1" cellpadding="5">
      <thead>
        <tr>
          <th>STT</th>
          <th>MSSV</th>
          <th>Họ tên</th>
          <th>Tuổi</th>
          <th>Hoạt động</th>
        </tr>
      </thead>

      <tbody>
        <tr v-for="(item, index) in list" :key="index">
          <td>{{ index + 1 }}</td>
          <td>{{ item.mssv }}</td>
          <td>{{ item.name }}</td>
          <td>{{ item.age }}</td>
          <td>         
             <button type="button" @click="handleDelete(index)">Delete</button>
             <button type="button">Edit</button>
          </td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<style scoped>

</style>
