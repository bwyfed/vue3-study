<template>
  <button @click="onClick">点击减1</button>
</template>

<script lang="ts" setup>
import { ref } from 'vue';
const num = ref<number>(100);
const onClick = () => {
  num.value += 1;
};
</script>
