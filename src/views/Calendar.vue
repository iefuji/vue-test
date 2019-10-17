<script>

import FullCalendar from '@fullcalendar/vue'
import timeGridPlugin from '@fullcalendar/timegrid'
import resourceTimeGridPlugin from '@fullcalendar/resource-timegrid'
import resourceTimeLinePlugin from '@fullcalendar/resource-timeline'
import resourceDayGridPlugin from '@fullcalendar/resource-daygrid'

export default {
  name: 'fullcalendar',
  components: {
    FullCalendar // make the <FullCalendar> tag available
  },
  head () {
    return {
      script: [
        { src: '@fullcalendar/moment/main.min.js' },
        { src: '@fullcalendar/core/locales/ja.js' },
        { src: '@fullcalendar/timegrid/main.js' },
        { src: '@fullcalendar/resource-common/main.js' },
        { src: '@fullcalendar/resource-timegrid/main.js' }
      ]
    }
  },
  data () {
    return {
      calendarPlugins: [ timeGridPlugin, resourceTimeGridPlugin, resourceDayGridPlugin, resourceTimeLinePlugin ],
      header: {
        left: 'today prev,next',
        center: 'title',
        right: 'dayGridMonth, resourceTimelineMonth, dayGridWeek, resourceTimeGridDay'
      },
      resources: [
        { id: '1', title: 'staff01' },
        { id: '2', title: 'staff02' },
        { id: '3', title: 'staff03' },
        { id: '4', title: 'staff04' },
        { id: '5', title: 'staff05' },
        { id: '6', title: 'staff06' },
        { id: '7', title: 'staff07' },
        { id: '8', title: 'staff08' },
        { id: '9', title: 'staff09' },
        { id: '10', title: 'staff10' },
        { id: '11', title: 'staff11' },
        { id: '12', title: 'staff12' },
        { id: '13', title: 'staff13' },
        { id: '14', title: 'staff14' },
        { id: '15', title: 'staff15' }
      ],
      buttonText: {
        today: '今日',
        month: '月',
        week: '週',
        day: '日'
      },
      events: [
        { resourceId: '1', title: 'care1', start: '2019-10-16T08:00', end: '2019-10-16T08:45' }
      ],
      timeFormat: 'HH:mm',
      slotDuration: '00:15:00',
      snapDuration: '01:00:00'
    }
  }
}

</script>

<template>
  <div class="FullCalendar">
    <h1>Hellow World</h1>
    <FullCalendar
      timeFormat="HH:mm"
      locale="ja"
      defaultView='resourceTimelineMonth'
      :plugins="calendarPlugins"
      :datesAboveResources="true"
      :header="header"
      :buttonText="buttonText"
      :resources="resources"
      :events="events"
 />
  </div>
</template>

<style lang='scss'>

@import '~@fullcalendar/core/main.css';
@import '~@fullcalendar/daygrid/main.css';
@import '~@fullcalendar/timegrid/main.css';
@import '~@fullcalendar/resource-timeline/main.css';

</style>
