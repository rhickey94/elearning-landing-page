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
    required: true,
  },
});
</script>
<template>
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
</template>
<style lang="scss" scoped>
.product-card {
  margin-top: 26px;
  max-width: 340px;
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
@media screen and (min-width: 1440px) {
  .product-card {
    max-width: 350px;
  }

  .card-container {
    padding: 32px 32px 40px 32px;
    height: 100%;
    h3 {
      font: 800 24px "Plus Jakarta Sans";
    }
    p {
      font: 500 18px/28px "Plus Jakarta Sans";
    }
    a:hover {
      color: var(--vt-c-pink);
    }
  }
}
</style>
