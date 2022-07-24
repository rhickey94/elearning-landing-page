<script setup>
import BasicButton from "./BasicButton.vue";
import { useMq } from "vue3-mq";

const mq = useMq();
console.log(mq);
</script>
<template>
  <header class="landing-footer">
    <div class="company-name">skilled</div>
    <BasicButton
      :bg-color="3"
      width="140px"
      height="48px"
      v-if="mq.mobile || mq.tablet"
      >Get Started</BasicButton
    >
    <BasicButton :bg-color="3" width="167px" height="56px" v-if="mq.desktop"
      >Get Started</BasicButton
    >
  </header>
</template>
<style lang="scss" scoped>
.landing-footer {
  background-color: var(--color-footer);
  color: var(--color-footer-text);
  padding: 16px;
  display: flex;
  align-items: center;
  justify-content: space-between;
}
.company-name {
  font: var(--heading-header);
}

@media screen and (min-width: 1440px) {
  .landing-footer {
    margin: 0 auto;
  }
}
</style>
