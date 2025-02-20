<template>
  <div>
    <main-section/>
    <timer-count/>
    <schedule-wedding/>
    <place-w/>
    <!-- <dress-code/> -->
    <!-- <detail-s/> -->

    <back-form/>
    <back-contact/>|
    <custom-footer/>
  </div>
</template>

<script>
import BackContact from './components/BackContact.vue'
import BackForm from './components/BackForm.vue'
import CustomFooter from './components/CustomFooter.vue'
// import DetailS from './components/DetailS.vue'
// import DressCode from './components/DressCode.vue'
import MainSection from './components/MainSection.vue'
import PlaceW from './components/PlaceW.vue'
import ScheduleWedding from './components/ScheduleWedding.vue'
import TimerCount from './components/TimerCount.vue'

export default {
  components: { MainSection, ScheduleWedding, PlaceW, BackForm, BackContact, CustomFooter, TimerCount,  },

}
</script>

<style>

</style>