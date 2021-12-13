<template>
  <h3>Trending Information Monitoring System </h3>
  <HelloWorld :width="1600" :height="500" />
  <DatepickerCom />
</template>

<script>
import { defineComponent } from 'vue'
import HelloWorld from './components/HelloWorld.vue'
import DatepickerCom from './components/DatePickerCom';
export default defineComponent({
  name: 'App',
  components: {
    HelloWorld,
    DatepickerCom
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
