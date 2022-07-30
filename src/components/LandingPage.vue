<script setup>
import BasicButton from "./BasicButton.vue";
import ProductCard from "./ProductCard.vue";

const products = [
  {
    id: 1,
    title: "Animation",
    textContent: `Learn the latest animation techniques to create stunning motion
            design and captivate your audience.`,
    imageLink: "/icon-animation.svg",
  },
  {
    id: 2,
    title: "Design",
    textContent: `Create beautiful, usable interfaces to help shape the future of how
            the web looks.`,
    imageLink: "/icon-design.svg",
  },
  {
    id: 3,
    title: "Photography",
    textContent: `Explore critical fundamentals like lighting, composition, and focus
            to capture exceptional photos.`,
    imageLink: "/icon-photography.svg",
  },
  {
    id: 4,
    title: "Crypto",
    textContent: `All you need to know to get started investing in crypto. Go from
beginner to advanced with this 54 hour course.`,
    imageLink: "/icon-crypto.svg",
  },
  {
    id: 5,
    title: "Business",
    textContent: `A step-by-step playbook to help you start, scale, and sustain your
business without outside investment.`,
    imageLink: "/icon-business.svg",
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
      <article class="hero-banner"></article>
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
  padding: 30px 16px;
  background: var(--color-background);
}
.hero-cta {
  display: flex;
  justify-content: center;
  flex-flow: row wrap;
}
.hero-cta-text {
  margin-top: 46px;
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
  height: 293px;
  width: 327px;
  background-image: url("../assets/image-hero-mobile.png");
  background-size: auto;
  background-position: top -28px left -54px;
  background-repeat: no-repeat;
  overflow: hidden;
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
    margin: 0 auto;
    margin-bottom: 193px;
    display: block;
    max-width: 1110px;
  }
  .hero-cta-text {
    padding-left: 17px;
  }
  .hero-banner {
    position: absolute;
    top: -200px;
    left: 350px;
    height: 640px;
    width: 640px;
    background-image: url("../assets/image-hero-tablet.png");
    background-size: auto;
    background-repeat: no-repeat;
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
  .hero-cta {
    margin-bottom: 193px;
  }
  .hero-cta-text {
    padding-left: 0px;
  }
  .hero-banner {
    top: -300px;
    left: 500px;
    height: 640px;
    width: 640px;
    background-image: url("../assets/image-hero-desktop.png");
    background-size: auto;
    background-repeat: no-repeat;
  }
  .product-information {
    gap: 56px 30px;
    margin: 0 auto 118px;
  }
  .product-cta {
    h2 {
      font: var(--heading-m);
    }
  }
}
</style>
