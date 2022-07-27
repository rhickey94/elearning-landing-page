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
        <picture>
          <source
            media="(min-width:1440px)"
            srcset="../assets/image-hero-desktop.png"
          />
          <source
            media="(min-width:768px)"
            srcset="../assets/image-hero-tablet.png"
          />
          <img src="../assets/image-hero-mobile.png" alt="hero" />
        </picture>
      </article>
    </section>
    <section class="product-information">
      <div class="product-cta">
        <h2>Check out our most popular courses!</h2>
      </div>
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
  display: flex;
  justify-content: center;
  flex-flow: row wrap;
  margin-bottom: 66px;
}
.hero-cta-text {
  margin-bottom: 46px;
  max-width: 398px;
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
  box-shadow: -95px 120px 63px -120px rgba(0, 0, 0, 0.66);
  width: 327px;
  display: flex;
  justify-content: center;
  // align-items: center;
  overflow: hidden;
  height: 321px;
  picture {
    clip-path: inset();
  }
  // img {
  //   // max-width: 100%;
  //   // max-height: 100%;
  // }
}
.product-information {
  margin: 0 auto 50px;
  display: flex;
  flex-flow: row wrap;
  justify-content: center;
  max-width: 1110px;
  gap: 16px;
}
.product-cta {
  background: var(--color-product-cta);
  color: var(--vt-c-white);
  padding: 28px;
  border-radius: 10px;
  max-width: 340px;
  margin-top: 24px;
  h2 {
    font: 800 24px/32px "Plus Jakarta Sans";
  }
}

@media screen and (min-width: 768px) {
  .hero-cta {
    margin-bottom: 93px;
  }
  .product-information {
    gap: 32px 11px;
  }
  .product-cta {
    h2 {
      margin-top: 28px;
    }
  }
}
@media screen and (min-width: 1440px) {
  .product-information {
    gap: 56px 30px;
    margin: 0 auto 118px;
  }
  .product-cta {
    h2 {
      // margin-top: 28px;
      font: var(--heading-m);
    }
  }
}
</style>
