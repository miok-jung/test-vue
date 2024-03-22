<template>
  <div>
    <h1>Index</h1>
    <ckeditor
      :editor="editor"
      v-model="editorData"
      :config="editorConfig"
    ></ckeditor>
  </div>
</template>

<script setup lang="ts">
import ClassicEditor from '@ckeditor/ckeditor5-build-classic';

const editor = ClassicEditor;

const editorData = '<p>Content of the editor.</p>';
const editorConfig = {
  // The configuration of the editor.
};
</script>

<style scoped></style>
