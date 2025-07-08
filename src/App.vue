<script setup>
import HeroSection from './components/HeroSection.vue'
import CalloutSection from './components/CalloutSection.vue'
import WhySection from './components/WhySection.vue'
import WhoWeServe from './components/WhoWeServe.vue'
import SneakPeek from './components/SneakPeek.vue'
import JoinList from './components/JoinList.vue'
import Footer from './components/Footer.vue'
import Navbar from './components/navbar/Navbar.vue'
</script>

<template>
  <div>
    <Navbar />
    <HeroSection />
    <CalloutSection />
    <WhySection />
    <WhoWeServe />
    <SneakPeek />
    <JoinList />
    <Footer />
  </div>
</template>

<style scoped>
body {
  font-family: 'Helvetica Neue', sans-serif;
  background-color: #fdfdfc;
  margin: 0;
}
</style>
