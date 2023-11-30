<script setup lang="ts">
import { ref, onBeforeMount } from 'vue';
const num = ref(0)
const arr: string[] = ["Working on it!", "Twiddling thumbs...", "Hard work", "Do you come here often?"]
function random() {
  num.value = Math.floor(Math.random() * arr.length)
}
onBeforeMount(() => {
  random()
})
</script>

<template>
  <div id="busy">{{ arr[num] }}</div>
</template>