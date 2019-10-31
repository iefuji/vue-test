<script>

import FullCalendar from '@fullcalendar/vue'
import timeGridPlugin from '@fullcalendar/timegrid'
import resourceTimeGridPlugin from '@fullcalendar/resource-timegrid'
import resourceTimeLinePlugin from '@fullcalendar/resource-timeline'
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
      calendarPlugins: [ timeGridPlugin, resourceTimeGridPlugin, resourceDayGridPlugin, resourceTimeLinePlugin, momentPlugin, interactionPlugin ],
      // ヘッダーのボタン位置とか
      header: {
        left: 'today prev,next',
        center: 'title',
        right: 'dayGridMonth, timeGridWeek, resourceTimeGridDay'
      },
      // ヘルパー名とか
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
      // 予定の内容
      events: [
        { resourceId: '1', title: 'care1', start: '2019-10-16T08:00', end: '2019-10-16T08:45' },
        { resourceId: '1', title: 'care1', start: '2019-10-16T09:00', end: '2019-10-16T09:30' },
        { resourceId: '1', title: 'care1', start: '2019-10-16T10:00', end: '2019-10-16T11:00' },
        { resourceId: '1', title: 'care1', start: '2019-10-16T11:30', end: '2019-10-16T14:00' },
        { resourceId: '1', title: 'care1', start: '2019-10-16T14:30', end: '2019-10-16T16:00' },
        { resourceId: '1', title: 'care1', start: '2019-10-16T16:30', end: '2019-10-16T17:30' },
        { resourceId: '1', title: 'care1', start: '2019-10-16T18:00', end: '2019-10-16T19:30' },
        { resourceId: '1', title: 'care1', start: '2019-10-16T20:00', end: '2019-10-16T21:45' },
        { resourceId: '1', title: 'care1', start: '2019-10-16T22:15', end: '2019-10-16T23:00' },
        { resourceId: '1', title: 'care1', start: '2019-10-16T23:30', end: '2019-10-16T24:00' }
      ],
      timeFormat: 'HH:mm',
      slotDuration: '00:05:00',
      snapDuration: '01:00:00',
      schedulerLicenseKey: 'GPL-My-Project-Is-Open-Source'
    }
  }
}

</script>

<template>
  <div class="FullCalendar">
    <!-- 表示確認用テキスト -->
    <h1>Calendar view test page</h1>
    <!-- export default > data > 各項目を設定、デフォルトから上書き -->
    <FullCalendar
      schedulerLicenseKey="GPL-My-Project-Is-Open-Source"
      timeFormat="HH:mm"
      locale="ja"
      defaultView='timeGridWeek'
      :plugins="calendarPlugins"
      :datesAboveResources="true"
      :header="header"
      :buttonText="buttonText"
      :resources="resources"
      :events="events"
      :weekNumbers="true"
      :editable="true"
      :selectable="true"
      :eventLimit="true"
      :weekends="true"
      :slotDuration="slotDuration"
      :snapDuration="snapDuration"
/>
  </div>
</template>

<style lang='scss'>

@import '~@fullcalendar/core/main.css';
@import '~@fullcalendar/daygrid/main.css';
@import '~@fullcalendar/timegrid/main.css';
@import '~@fullcalendar/resource-timeline/main.css';

</style>
