<template>
  <section class="hero-section">
    <div class="container text-white text-center">
      <h1 class="font-size">Rent a serene therapy room by the hour</h1>
      <h1 class="font-size">and grow your practice on your own terms.</h1>
    </div>
  </section>
</template>

<style scoped>
.hero-section {
  position: relative;
  min-height: 55vh;
  padding-top: 3rem;

  background-image:
    linear-gradient(
      to bottom,
      rgba(255, 255, 255, 0.3) 0%,
      rgba(255, 255, 255, 0.3) 35%,
      rgba(255, 255, 255, 0) 75%
    ),
    url('@/assets/images/Slider.png');

  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
}

.container {
  max-width: 900px;
  margin: 0 auto;
}

.font-size {
  color: #fff;
  font-weight: 400;
  text-shadow:
    0 1px 1px rgba(0, 0, 0, 0.7),
    0 0 1px rgba(255, 255, 255, 0.7);

  font-size: 2rem;
  line-height: 1.2;
}

@media (max-width: 768px) {
  .font-size {
    font-size: 1.5rem;
  }

  .hero-section {
    padding-top: 2rem;
  }
}

@media (max-width: 480px) {
  .font-size {
    font-size: 1.2rem;
  }

  .hero-section {
    padding-top: 1.5rem;
  }
}
</style>
