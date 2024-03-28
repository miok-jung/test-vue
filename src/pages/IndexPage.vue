<template>
  <div>
    <h1>Index</h1>
    <!-- editor: ClassicEditor / InlineEditor -->
    <!-- <ckeditor
      :editor="ClassicEditor"
      v-model="editorData"
      :config="editorConfig"
      :disabled="true"
    /> -->
    <ckeditor
      :editor="InlineEditor"
      v-model="inlineEditorData"
      :config="inlineEditorConfig"
    />
  </div>
</template>

<script setup lang="ts">
// import ClassicEditor from '@ckeditor/ckeditor5-build-classic';
import InlineEditor from '@ckeditor/ckeditor5-build-inline';
import '@ckeditor/ckeditor5-build-classic/build/translations/ko';

// NOTE: Classic Editor
// const editorData = '<p>내용을 입력하세요.</p>';
// const editorConfig = {
//   language: 'ko',
//   // toolbar: ['bold', 'italic', '|', 'link'],
// };

// NOTE: Inline Editor
const inlineEditorData = '';
const inlineEditorConfig = {
  language: 'ko',
};
</script>

<style scoped></style>
