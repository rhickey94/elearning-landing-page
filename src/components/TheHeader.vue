<script setup>
import BasicButton from "./BasicButton.vue";
import { useMq } from "vue3-mq";

const mq = useMq();
console.log(mq);
</script>
<template>
  <header class="landing-header">
    <div class="header-container">
      <div class="company-name">skilled</div>
      <BasicButton width="140px" height="48px" v-if="mq.mobile || mq.tablet"
        >Get Started</BasicButton
      >
      <BasicButton width="167px" height="56px" v-if="mq.desktop"
        >Get Started</BasicButton
      >
    </div>
  </header>
</template>
<style lang="scss" scoped>
.landing-header {
  padding: 16px;
  display: flex;
  justify-content: center;
}
.header-container {
  display: flex;
  align-items: center;
  justify-content: space-between;
  flex-grow: 1;
  max-width: 1080px;
}
.company-name {
  font: 800 28px "Plus Jakarta Sans";
}

@media screen and (min-width: 1440px) {
  .landing-header {
    margin: 0 auto;
  }
  .company-name {
    font: 800 36px "Plus Jakarta Sans";
  }
}
</style>
