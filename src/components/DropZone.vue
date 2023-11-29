<script setup lang="ts">

</script>

<template>
    <div class="dropzone">
        <span>Drag and Drop File</span>
        <span>OR</span>
        <label for="dropzonefile">Select File</label>
        <input type="file" id="dropzonefile" />
    </div>
</template>

<style scoped>
.dropzone{
    display: flex;
    justify-content: center;
    flex-direction: column;
}
input{
    display: none;
}
</style>