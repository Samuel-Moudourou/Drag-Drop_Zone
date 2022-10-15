<template>
    <div 
    @dragenter.prevent="toggleActive"
    @dragleave.prevent="toggleActive"
    @dragover.prevent
    @drop.prevent="toggleActive"

    :class="{'active-dropzone' : active }"
    class="dropzone">
        <span>Drag or Drop File</span>
        <span>OR</span>
        <label for="dropzoneFile">Select File</label>
        <input type="file"  id="dropzoneFile" class="dropzoneFile">
    </div>
</template>



<script setup>
import { ref } from "vue";


const active = ref(false);

// passage de la classe "dropzone" en mode active-desactive

const toggleActive = () => {
    active.value = !active.value;
};



</script>



<style scoped>
.dropzone{
    width: 600px;
    height: 200px;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    background-color: rgb(241, 255, 250);
    border-radius: 10px;
    gap: 16px;
    border: 2px dashed aquamarine;
    transition: 0.3s ease-in-out all;


    }
.dropzone > label{
        padding: 8px 12px;
        color: #fff;
        background-color: rgb(0, 224, 150);
        transition: 0.3s ease-in-out all;
        border-radius: 5px;
    }

.dropzone > input{
    display: none;
}

.active-dropzone{
    background-color:  rgba(0, 44, 29, 0.603);
    border: 2px dashed rgb(1, 247, 165);
    color: #fff;

}

.active-dropzone > label{
    color: rgb(0, 194, 129);
    background-color: rgb(255, 255, 255);
}

</style>