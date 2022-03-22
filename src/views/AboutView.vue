<template>
  <Datepicker v-model="date" :minDate="new Date().toISOString().substr(0, 10)" 
  :disabledWeekDays="[0]"
   :enableTimePicker="false"></Datepicker>

   <Datepicker v-model="time" timePicker :is24="false"
    :minTime="{ hours: 8, minutes: 30 }" :maxTime="{ hours: 16, minutes: 50 }" />
</template>

<script>
import Datepicker from '@vuepic/vue-datepicker';
import '@vuepic/vue-datepicker/dist/main.css'
import { ref } from 'vue';
export default {
 components: { Datepicker },
         setup() {
        const date = ref();
         const time = ref({ 
            hours: new Date().getHours(),
            minutes: new Date().getMinutes()
        });
        
        return {
            date,
            time
        }
    }
}
</script>
