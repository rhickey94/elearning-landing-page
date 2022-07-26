<script setup>
import BasicButton from "./BasicButton.vue";
import { useMq } from "vue3-mq";

const mq = useMq();
console.log(mq);
</script>
<template>
  <header class="landing-header">
    <div class="company-name">skilled</div>
    <BasicButton width="140px" height="48px" v-if="mq.mobile || mq.tablet"
      >Get Started</BasicButton
    >
    <BasicButton width="167px" height="56px" v-if="mq.desktop"
      >Get Started</BasicButton
    >
  </header>
</template>
<style lang="scss" scoped>
.landing-header {
  padding: 16px;
  display: flex;
  align-items: center;
  justify-content: space-between;
}
.company-name {
  font: 800 28px "Plus Jakarta Sans";
}

@media screen and (min-width: 1440px) {
  .landing-header {
    margin: 0 auto;
  }
}
</style>
