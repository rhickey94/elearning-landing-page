<script setup>
import BasicButton from "./BasicButton.vue";
import ProductCard from "./ProductCard.vue";

const products = [
  {
    id: 1,
    title: "Animation",
    textContent: `Learn the latest animation techniques to create stunning motion
            design and captivate your audience.`,
    imageLink: "../src/assets/icon-animation.svg",
  },
  {
    id: 2,
    title: "Design",
    textContent: `Create beautiful, usable interfaces to help shape the future of how
            the web looks.`,
    imageLink: "../src/assets/icon-design.svg",
  },
  {
    id: 3,
    title: "Photography",
    textContent: `Explore critical fundamentals like lighting, composition, and focus
            to capture exceptional photos.`,
    imageLink: "../src/assets/icon-photography.svg",
  },
  {
    id: 4,
    title: "Crypto",
    textContent: `All you need to know to get started investing in crypto. Go from
beginner to advanced with this 54 hour course.`,
    imageLink: "../src/assets/icon-crypto.svg",
  },
  {
    id: 5,
    title: "Business",
    textContent: `A step-by-step playbook to help you start, scale, and sustain your
business without outside investment.`,
    imageLink: "../src/assets/icon-business.svg",
  },
];
</script>
<template>
  <main>
    <section class="hero-cta">
      <article class="hero-cta-text">
        <h1>Maximize skill, minimize budget</h1>
        <p>
          Our modern courses across a range of<br />in-demand skills will give
          you the knowledge you need to live the life you want.
        </p>
        <BasicButton :bg-color="2" width="167px" height="56px"
          >Get Started</BasicButton
        >
      </article>
      <article class="hero-banner">
        <img src="../assets/image-hero-mobile.png" alt="hero" />
      </article>
    </section>
    <section class="product-information">
      <h2>Check out our most popular courses!</h2>
      <ProductCard
        v-for="product in products"
        :key="product.id"
        :title="product.title"
        :text-content="product.textContent"
        :image-link="product.imageLink"
      />
    </section>
  </main>
</template>
<style lang="scss" scoped>
main {
  padding: 22px 16px;
  background: var(--color-background);
}
.hero-cta {
  margin-bottom: 66px;
}
.hero-cta-text {
  margin-bottom: 46px;
  h1 {
    font: var(--heading-l);
    margin-bottom: 26px;
  }
  p {
    color: var(--vt-c-gray);
    font: var(--body-s);
    margin-bottom: 24px;
  }
}
.hero-banner {
  display: flex;
  justify-content: center;
  align-items: center;
  overflow: hidden;
  width: 328px;
  height: 302px;
  img {
    // max-width: 100%;
    // max-height: 100%;
  }
}
.product-information {
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  margin-bottom: 50px;
  gap: 16px;
  h2 {
    background: var(--color-product-cta);
    color: var(--vt-c-white);
    font: 800 24px/32px "Plus Jakarta Sans";
    padding: 28px;
    border-radius: 10px;
  }
}
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
