<script setup>
import DropZone from '../components/DropZone.vue';
import { ref } from "vue";

let dropzoneFile = ref("");

// choisir le fichier par drag & drop

const drop = (e) => {
  dropzoneFile.value = e.dataTransfer.files[0];
};

// choisir le fichier en cliquant sur le bouton "selectfile"

const selectedFile = () => {
  dropzoneFile.value = document.querySelector(".dropzoneFile").files[0];
};
</script>

<template>
  <div class="home">
    <h1>Drop your file here</h1>
    <DropZone @drop.prevent="drop" @change="selectedFile"/>
    <span class="file-info">File: {{dropzoneFile.name}}</span>
  </div>
</template>


<style>
.home{
  width: 100vw;
  height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  gap: 32px;
}
</style>
