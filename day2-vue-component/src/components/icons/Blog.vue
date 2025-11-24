<script setup>
    import { ref } from 'vue';
    const message = ref()
</script>
<template>
    
<div class="container py-4">
  <label for="editor" class="form-label">Soạn thảo nội dung</label>
  
  <!-- Vùng nhập liệu -->
  <div id="editor"
       class="form-control"
       contenteditable="true"
       style="min-height:200px;"
       role="textbox"
       aria-label="Soạn thảo nội dung">
    <p>Bạn có thể viết đoạn văn dài ở đây...</p>
  </div>

  <!-- Nút chèn hình ảnh -->
  <div class="mt-3">
    <input type="file" id="imageInput" accept="image/*" class="form-control mb-2">
    <button id="insertImageBtn" class="btn btn-success">Chèn hình ảnh</button>
  </div>

  <!-- Nút lấy nội dung -->
  <button id="getContentBtn" class="btn btn-primary mt-3">Lấy nội dung</button>
  <pre id="result" class="mt-2"></pre>
</div>

    
</template>
<style scoped>
    
</style>