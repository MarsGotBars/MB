<script setup lang="ts">
import Progress from './Progress.vue'
import { ref } from 'vue';
defineProps({
    DropZoneFile: File
})
const inProgress = ref(false)
const active = ref(false)
function boolSwap() {
    inProgress.value = !inProgress.value;
}

const toggleActive = () => {
    active.value = !active.value
    return { active, toggleActive }
}


</script>

<template>
    <div class="dropzone" 
        @dragenter.prevent="toggleActive" 
        @dragleave.prevent="toggleActive" 
        @dragover.prevent
        @drop.prevent="toggleActive"
        :class="{ 'active-drop' : active }"
        >
        <span>Drag and Drop File</span>
        <span>OR</span>
        <label for="dropzonefile">Select File</label>
        <input type="file" id="dropzonefile" />
        <!-- TODO: weird check, have to look at this later -->
        <span>File: {{DropZoneFile?.name != "File" ? DropZoneFile?.name : "None selected"}}</span>
        <span v-if="DropZoneFile?.size != null">Size: {{(DropZoneFile.size/1024/1024).toFixed(1)}}</span>
        <button v-if="inProgress != true" @click="boolSwap()">test</button>
        <div v-if="inProgress === true"><Progress /></div>
    </div>
</template>

<style scoped>
.dropzone {
    display: flex;
    justify-content: center;
    flex-direction: column;
    align-items: center;
    transition: 0.3s ease all;
    padding: 2rem;
    border-radius: 1rem;
}

.active-drop{
    background: #42b8839c;
}

input {
    display: none;
}
</style>