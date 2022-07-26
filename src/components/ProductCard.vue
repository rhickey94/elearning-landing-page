<script setup>
defineProps({
  title: {
    type: String,
    required: true,
  },
  textContent: {
    type: String,
    required: true,
  },
  imageLink: {
    type: String,
    required: true,
  },
});
</script>
<template>
  <main>
    <article class="product-card">
      <div class="card-container">
        <img :src="imageLink" alt="animation" />
        <h3>{{ title }}</h3>
        <p>
          {{ textContent }}
        </p>
        <a href="/">Get Started</a>
      </div>
    </article>
  </main>
</template>
<style lang="scss" scoped>
.product-card {
  margin-top: 26px;
}

.card-container {
  position: relative;
  background: var(--vt-c-white);
  padding: 28px 28px 32px 28px;
  border-radius: 10px;
  box-shadow: 0px 25px 50px rgba(6, 22, 141, 0.0442381);

  img {
    position: absolute;
    top: -24px;
    left: 24px;
    z-index: 100;
  }
  h3 {
    margin-top: 28px;
    color: var(--vt-c-dark-blue);
    font: 800 20px "Plus Jakarta Sans";
    margin-bottom: 16px;
  }
  p {
    color: var(--vt-c-gray);
    font: 500 16px/26px "Plus Jakarta Sans";
    margin-bottom: 24px;
  }
  a {
    text-decoration: none;
    color: var(--vt-c-hot-pink);
    font: 700 18px/28px "Plus Jakarta Sans";
  }
}
</style>
