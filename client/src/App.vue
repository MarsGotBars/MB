<script setup lang="ts">
import { ref } from 'vue';
import DropZone from './components/DropZone.vue'
const DropZoneFile = ref(File || null)

const validate = (e:any) => {
  // TODO: validate max size of file here, most likely 300MB
  drop(e)
}
const drop = (e:any) => {
    DropZoneFile.value = e.dataTransfer.files[0]
    return {DropZoneFile, drop}
  }
</script>

<template>
  <main>
    <DropZone @drop.prevent="validate" :DropZoneFile="DropZoneFile" />
  </main>
</template>