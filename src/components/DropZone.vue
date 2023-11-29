<script setup lang="ts">
import Progress from './Progress.vue'
import { ref } from 'vue';
defineProps({
  dropzonefile: File
})
const inProg = ref(false)
const active = ref(false)
function boolSwap() {
    inProg.value = !inProg.value;
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
        <span>File: {{dropzonefile?.name}}</span>
        <button v-if="inProg != true" @click="boolSwap()">test</button>
        <div v-if="inProg === true"><Progress /></div>
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