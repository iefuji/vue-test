<template>
<div class="fullcalendar">
  <FullCalendar
  @dateClick="handleDateClick"
  defaultView="dayGridMonth"
  ref="fullCalendar"
  :plugins="calendarPlugins"
  :weekends="false"
  :events="[
    { title: 'event 1', date: '2019-10-01' },
    { title: 'event 2', date: '2019-10-10' }
  ]"
  />
</div>

</template>

<script>

import FullCalendar from '@fullcalendar/vue'
import dayGridPlugin from '@fullcalendar/daygrid'

export default {
  components: {
    FullCalendar // make the <FullCalendar> tag available
  },
  data () {
    return {
      calendarPlugins: [ dayGridPlugin ]
    }
  },
  methods: {
    handleDateClick (arg) {
      alert(arg.date)
    }
  }
}

</script>

<style lang='scss'>

@import '~@fullcalendar/core/main.css';
@import '~@fullcalendar/daygrid/main.css';

</style>
