<template>
  <section class="py-5">
    <div class="container">
      <h2 class="text-center mb-5">Who <span class="text-titled">We</span> Serve</h2>
      <div class="row">
        <item-serve class="mt-3" v-for="(item, index) in serves" :key="index" :icon="item.icon" :title="item.title"
          :text="item.text" :background="item.background" :titleColor="item.titleColor" :isList="item.isList"
          :listItemsLines="item.listItemsLines" />
      </div>
    </div>
  </section>
</template>

<script setup>
import ItemServe from './ItemServe.vue';
import serve1 from '@/assets/images/serve-1.png'
import serve2 from '@/assets/images/serve-2.png'
import Icon5 from '@/assets/icon-set/Lathera Icons-05.svg'
import Icon6 from '@/assets/icon-set/Lathera Icons-06.svg'
const serves = [
  {
    icon: Icon5,
    title: 'Licensed Professionals',
    text: 'Psychologists, LMFTs, LCSWs, Coaches, Nutritionists, Life Coaches, Therapists',
    listItemsLines: [
      ['Psychologists', 'LMFTs', 'LCSWs', 'Coaches'],
      ['Nutritionists', 'Body-work Therapist']
    ],
    background: `url(${serve1})`,
    titleColor: "#D2B8A3",
    isList: true
  },
  {
    icon: Icon6,
    title: 'Clients & Patients',
    text: 'Searching for the right therapist?\nOur public directory (launching soon)\n will let you filter by specialty,\nlanguage, insurance, and more.',
    background: `url(${serve2})`,
    titleColor: "#8C9B8B",
    isList: false
  }

];
</script>

<style scoped>
.text-titled {
  color: #D2B8A3;
}
</style>
