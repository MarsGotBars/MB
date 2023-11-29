<script setup lang="ts">
import { ref } from 'vue';
import DropZone from './components/DropZone.vue'
const dropzonefile = ref(null)
const drop = (e:any) => {
    dropzonefile.value = e.dataTransfer.files[0]
    return {dropzonefile, drop}
}
</script>

<template>
  <main>
    <DropZone @drop.prevent="drop" :dropzonefile="dropzonefile" />
  </main>
</template>