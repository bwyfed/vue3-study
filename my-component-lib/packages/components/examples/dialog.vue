<template>
  <button @click="onClick">点击打开对话框</button>
</template>

<script setup lang="ts">
import { Dialog } from "../src";

const onClick = () => {
  const dialog = Dialog.createDialog({
    text: "您好,我是对话框组件",
    onOk: () => {
      dialog.close();
    },
  });
};
</script>
