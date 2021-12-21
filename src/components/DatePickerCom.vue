<template>
  <Datepicker v-model="date" dark range locale="de-DE" monthNameFormat="long" :format="'dd.MM.yyyy HH:mm'" cancelText="abbrechen" selectText="auswählen" showNowButton nowButtonLabel="jetzt" :is24="true">
  <template #calendar-header="{ index, day }">
    <div :class="index === 5 || index === 6 ? 'weekend-color' : ''">
      {{ day }}
    </div>
  </template>
  </Datepicker>
</template>

<script>
import Datepicker from 'vue3-date-time-picker';
import 'vue3-date-time-picker/dist/main.css';
import { ref, onMounted } from 'vue';

export default {
  name: "DatePickerCom",
  components: { Datepicker },

  setup() {
    const date = ref();

    // For demo purposes assign range from the current date
    onMounted(() => {
      const startDate = new Date();
      const endDate = new Date(new Date().setDate(startDate.getDate() + 7));
      date.value = [startDate, endDate];
    })

    return {
      date,
    }
  }
}
</script>


<style>
.weekend-color {
  color: #773232;
}

.dp__theme_dark {
  --dp-background-color: #212121;
  --dp-text-color: #ffffff;
  --dp-hover-color: #484848;
  --dp-hover-text-color: #ffffff;
  --dp-hover-icon-color: #959595;
  --dp-primary-color: #005cb2;
  --dp-primary-text-color: #ffffff;
  --dp-secondary-color: #a9a9a9;
  --dp-border-color: #2d2d2d;
  --dp-border-color-hover: #aaaeb7;
  --dp-disabled-color: #737373;
  --dp-scroll-bar-background: #212121;
  --dp-scroll-bar-color: #484848;
  --dp-success-color: #00701a;
  --dp-success-color-disabled: #428f59;
  --dp-icon-color: #959595;
  --dp-danger-color: #e53935;
}

.dp__input_wrap {
  position: relative;
  width: 420px;
  box-sizing: unset;
}




</style>