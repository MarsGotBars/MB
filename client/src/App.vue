<script setup lang="ts">
import { ref } from 'vue';
import DropZone from './components/DropZone.vue'
const dropzonefile = ref(File || null)

const validate = (e:any) => {
  drop
  return {dropzonefile, drop}
}
const drop = (e:any) => {
    dropzonefile.value = e.dataTransfer.files[0]
    
  }
</script>

<template>
  <main>
    <DropZone @drop.prevent="validate" :dropzonefile="dropzonefile" />
  </main>
</template>