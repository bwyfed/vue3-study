<template>
  <div :class="[`${prefixName}-box`, className]">
    <slot v-if="$slots.default"></slot>
  </div>
</template>

<script setup lang="ts">
import { prefixName } from '../theme/index';
defineProps({className: String});
</script>
