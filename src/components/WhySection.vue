<template>
  <section class="py-5 bg-light">
    <div class="container">
      <div class="row align-items-center">
        <div class="col-md-6">
          <div class="w-70 mx-auto">
            <h2 class="mb-4">
              Why <span class="fw-bold" style="color: #5a7263">LaThera</span> Space?
            </h2>
            <div class="row">
              <div class="col-12 mb-4" v-for="(reason, index) in reasons" :key="index">
                <reason :icon="reason.icon" :title="reason.title" :text="reason.text" :index="index + 1" />
              </div>
            </div>
          </div>
        </div>
        <div class="col-md-6">
          <img src="@/assets/images/Why Lathera.png" alt="Why Choose" class="img-fluid rounded shadow-sm" />
        </div>
      </div>
    </div>
  </section>

</template>

<script setup>
import Reason from './Reason.vue';
import Icon2 from '@/assets/icon-set/Lathera Icons-02.svg'
import Icon1 from '@/assets/icon-set/Lathera Icons-01.svg'
import Icon3 from '@/assets/icon-set/Lathera Icons-03.svg'
import Icon4 from '@/assets/icon-set/Lathera Icons-04.svg'

const reasons = [
  {
    icon: Icon2,
    title: 'No Contracts. No Hassle.',
    text: 'Reserve the hour, half-day, or full company day that fits your schedule.'
  },
  {
    icon: Icon1,
    title: 'Designed for Well-Being',
    text: 'Natural light, sound panels and comfortable décor elevate your experience for both you and your clients.'
  },
  {
    icon: Icon3,
    title: 'Built-In Marketing',
    text: 'Be seen by those seeking care with our built-in directory and marketing.'
  },
  {
    icon: Icon4,
    title: 'All-Inclusive Amenities',
    text: 'High-speed WiFi, printing, coffee/tea, front desk support and furnished waiting area included.'
  }
];
</script>

<style scoped>
h2 span {
  color: #5a7263;
}
.w-70 {
  width: 70%;
}
</style>
