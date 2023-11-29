<script setup lang="ts">
const arr: string[] = ["Working on it!", "widdling thumbs...", "Hard work", "Do you come here often?"]
</script>

<template>
  <!-- TODO: only appear whilst working on upload -->
  <div id="test">{{arr[Math.floor(Math.random() * arr.length)]}}</div>
</template>