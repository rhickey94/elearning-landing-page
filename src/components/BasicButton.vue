<script setup>
import { computed } from "vue";

const colors = {
  1: {
    color: "var(--color-button-1)",
    hover: "var(--color-button-1-hover)",
  },
  2: {
    color: "var(--color-button-2)",
    hover: "var(--color-button-2-hover)",
  },
  3: {
    color: "var(--color-button-3)",
    hover: "var(--color-button-3-hover)",
  },
};

const props = defineProps({
  bgColor: {
    type: Number,
    default: 1,
  },
  width: {
    type: String,
    default: "167px",
  },
  height: {
    type: String,
    default: "56px",
  },
});

const cssVars = computed(() => {
  return {
    "--bg-color": colors[props.bgColor].color,
    "--bg-color-hover": colors[props.bgColor].hover,
    "--btn-width": props.width,
    "--btn-height": props.height,
  };
});
</script>
<template>
  <button type="button" class="button" :style="cssVars">
    <slot></slot>
  </button>
</template>
<style lang="scss" scoped>
.button {
  width: var(--btn-width);
  height: var(--btn-height);
  background: var(--bg-color);
  border: none;
  border-radius: 28px;
  font: var(--body-m);
  color: var(--color-button-text);
}
.button:hover {
  background: var(--bg-color-hover);
}
</style>
