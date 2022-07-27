<script setup>
import BasicButton from "./BasicButton.vue";
import { useMq } from "vue3-mq";

const mq = useMq();
console.log(mq);
</script>
<template>
  <footer class="landing-footer">
    <div class="footer-container">
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
    </div>
  </footer>
</template>
<style lang="scss" scoped>
.landing-footer {
  background-color: var(--vt-c-dark-blue);
  color: var(--vt-c-white);
  padding: 16px;
  height: 120px;
  display: flex;
  justify-content: center;
}
.footer-container {
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
  .footer-container {
    max-width: 1080px;
  }
  .landing-footer {
    margin: 0 auto;
  }
  .company-name {
    font: 800 36px "Plus Jakarta Sans";
  }
}
</style>
