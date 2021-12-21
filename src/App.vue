<template>
  <h3>Trending Information Monitoring System </h3>
  <DatepickerCom />
   <HelloWorld :width="1600" :height="500" />
  <Selectfields />
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import DatepickerCom from './components/DatePickerCom'
import Selectfields from './components/Selectfields'

export default defineComponent({
  name: 'App',
  components: {
    HelloWorld,
    DatepickerCom,
    Selectfields
  }
})


</script>

<style>
#app {
  font-family: "Arial", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  /*color: #2c3e50;*/
  color: red;
  margin-top: 60px;

}
h3 {
  color: turquoise;
  font-size: 2rem;
}


</style>
