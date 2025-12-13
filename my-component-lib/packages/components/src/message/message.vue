<template>
  <transition :name="fadeClassName">
    <div v-if="show" :class="{ [baseClassName]: true, [typeClassName]: true }">
      <div>{{ props.text }}</div>
    </div>
  </transition>
</template>
<script lang="ts" setup>
import { ref, onMounted } from "vue";
import { prefixName } from "../theme";
import type { MessageType } from "./types";

const show = ref<boolean>(false);

onMounted(() => {
  show.value = true;
});

const props = withDefaults(
  defineProps<{ type?: MessageType; text?: string; duration?: number }>(),
  {
    type: "info",
    duration: 3000,
  }
);

const closeMessage = () => {
  show.value = false;
};

defineExpose({ closeMessage: closeMessage });

const baseClassName = `${prefixName}-message`;
const typeClassName = `${baseClassName}-${props.type}`;
const fadeClassName = `${baseClassName}-fade`;
</script>
