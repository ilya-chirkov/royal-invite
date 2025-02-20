<template>
  <div>
    <live-back/>
    <main-section/>
    <timer-count/>
    <schedule-wedding/>
    <place-w/>
    <dress-code/>
    <details-part/>

    <back-form/>
    <back-contact/>|
    <custom-footer/>
  </div>
</template>

<script>
import BackContact from './components/BackContact.vue'
import BackForm from './components/BackForm.vue'
import CustomFooter from './components/CustomFooter.vue'
import DetailsPart from './components/DetailsPart.vue'
import DressCode from './components/DressCode.vue'
import MainSection from './components/MainSection.vue'
import PlaceW from './components/PlaceW.vue'
import ScheduleWedding from './components/ScheduleWedding.vue'
import TimerCount from './components/TimerCount.vue'

export default {
  components: { MainSection, ScheduleWedding, PlaceW, BackForm, BackContact, CustomFooter, TimerCount, DetailsPart, DressCode},

}
</script>

<style>
* {
    box-sizing: border-box;
    padding: 0;
  }
  *,
  body {
    margin: 0;
  }
  body {
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    background-image: url(./assets/back.d35585ec7f726f15f575.png);
    background-position: 50%;
    background-repeat: no-repeat;
    background-size: cover;
    font-family: -apple-system, BlinkMacSystemFont, Open Sans, Roboto, Oxygen,
      Ubuntu, Cantarell, Fira Sans, Droid Sans, Helvetica Neue, sans-serif;
  }
  @font-face {
    font-display: swap;
    font-family: KyivType Sans;
    src: local("KyivType Sans"),
      url(./assets/KyivTypeSans-VarGX.ttf);
  }
  code {
    font-family: source-code-pro, Menlo, Monaco, Consolas, Courier New, monospace;
  }
  html {
    max-width: 100%;
    width: 100%;
  }
  body,
  html {
    overflow-x: hidden;
  }
</style>