<script>

import FullCalendar from '@fullcalendar/vue'
import dayGridPlugin from '@fullcalendar/daygrid'
import timeGridPlugin from '@fullcalendar/timegrid'
import resourceTimeGridPlugin from '@fullcalendar/resource-timegrid'
import resourceDayGridPlugin from '@fullcalendar/resource-daygrid'
import momentPlugin from '@fullcalendar/moment'
import interactionPlugin from '@fullcalendar/interaction'

export default {
  name: 'fullcalendar',
  components: {
    FullCalendar // make the <FullCalendar> tag available
  },
  head () {
    return {
      link: [
        { rel: 'stylesheet', href: '/css/fullcalendar.min.css' },
        { rel: 'stylesheet', href: 'node_modules/@fullcalendar/core/main.css' },
        { rel: 'stylesheet', href: 'node_modules/@fullcalendar/daygrid/main.css' }
      ],
      script: [
        { src: '@fullcalendar/moment/main.min.js' },
        { src: '@fullcalendar/core/locales/ja.js' }
      ]
    }
  },
  data () {
    return {
      calendarPlugins: [ interactionPlugin, dayGridPlugin, timeGridPlugin, momentPlugin, resourceTimeGridPlugin, resourceDayGridPlugin ],
      defaultView: 'resourceTimelineDay',
      header: {
        left: 'today prev,next',
        center: 'title',
        right: 'dayGridMonth, dayGridWeek, dayGridDay'
      },
      resources: [
        { id: 'a', title: 'Staff 01' },
        { id: 'b', title: 'Staff 02' },
        { id: 'c', title: 'Staff 03' }
      ],
      events: [
        { title: 'event1', start: '2019-10-01' },
        { title: 'event2', start: '2019-10-02T12:00', end: '2019-10-31T14:00' },
        { title: 'event3', start: '2019-10-03', allDay: true }
      ],
      buttonText: {
        today: '今日',
        month: '月',
        week: '週',
        day: '日'
      },
      editable: true,
      selectable: true,
      selectHelper: true,
      eventLimit: false,
      firstDay: 0,
      weekends: true,
      weekNumbers: true,
      timeFormat: 'HH:mm',
      slotDuration: '00:15:00',
      snapDuration: '01:00:00'
    }
  }
}

</script>

<template>
  <div class="card-body">
    <p>test</p>
    <div id="FullCalendar">
      <FullCalendar
        schedulerLicenseKey="GPL-My-Project-Is-Open-Source"
        timeFormat="HH:mm"
        locale="ja"
        :plugins="calendarPlugins"
        :header="header"
        :events="events"
        :buttonText="buttonText"
        :editable="true"
        :selectable="true"
        :eventLimit="false"
        :firstDay="0"
        :weekends="true"
        :weekNumbers="true"
        :slotDuration="slotDuration"
        :snapDuration="snapDuration"
      />
    </div>
  </div>
</template>

<style lang='scss'>

@import '~@fullcalendar/core/main.css';
@import '~@fullcalendar/daygrid/main.css';

</style>
