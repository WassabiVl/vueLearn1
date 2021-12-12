<template>
  <div>
    <h3>Trending Information Monitoring System </h3>
    <HelloWorld :width="1600" :height="500" />
    <Datepicker v-model="date"></Datepicker>
  </div>

</template>




<script>
import { defineComponent } from 'vue'
import HelloWorld from './components/HelloWorld.vue'

export default defineComponent({
  name: 'App',
  components: {
    HelloWorld
  }
})
</script>

<script>
import Datepicker from 'vue3-date-time-picker';
import 'vue3-date-time-picker/dist/main.css'

export default {
  components: { Datepicker },
  data() {
    return {
      date: null,
    };
  }
}
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
