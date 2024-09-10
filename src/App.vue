<template>
  <Page1></Page1>
  <Page2></Page2>
  <Page5></Page5>
  <Page3></Page3>
  <!-- <Page4 ></Page4> -->
  <Comparison></Comparison>
  <Page8></Page8>
  <!-- <Page7 ></Page7> -->
  <FeaturesSection />
  <Page5a></Page5a>
  <Page6></Page6>
  <Page6a></Page6a>
  <!-- <Caraosuel></Caraosuel> -->
  <!-- <Page8 class="page8"></Page8> -->
</template>

<style>
* {
  margin: 0;
  padding: 0;
  font-family: system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto,
    Oxygen, Ubuntu, Cantarell, "Open Sans", "Helvetica Neue", sans-serif;
}
html,
body {
  height: 100%;
}
</style>

<script>
export default {
  mounted() {
    const observerOptions = {
      threshold: 0.1,
    };

    const observerCallback = (entries) => {
      entries.forEach((entry) => {
        if (entry.isIntersecting) {
          entry.target.classList.add("visible");
        } else {
          entry.target.classList.remove("visible");
        }
      });
    };

    const observer = new IntersectionObserver(
      observerCallback,
      observerOptions
    );
    const targets = document.querySelectorAll(
      ".zurag, .left-text, .object-zurag, .big-text, .column, .long-text, .hero-title, .hero-subtitle, .haptic-zuun, .adap-zuun"
    );
    targets.forEach((target) => {
      observer.observe(target);
    });
  },
};
</script>
