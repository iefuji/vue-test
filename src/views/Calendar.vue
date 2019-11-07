<script>

import Vue from 'vue'
import FullCalendar from '@fullcalendar/vue'
import timeGridPlugin from '@fullcalendar/timegrid'
import resourceTimeGridPlugin from '@fullcalendar/resource-timegrid'
import resourceTimeLinePlugin from '@fullcalendar/resource-timeline'
import resourceDayGridPlugin from '@fullcalendar/resource-daygrid'
import momentPlugin from '@fullcalendar/moment'
import interactionPlugin from '@fullcalendar/interaction'
import VTooltip from 'v-tooltip'

Vue.use(VTooltip)

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
    const vm = this
    return {
      calendarPlugins: [ timeGridPlugin, resourceTimeGridPlugin, resourceDayGridPlugin, resourceTimeLinePlugin, momentPlugin, interactionPlugin ],
      // ヘッダーのボタン位置とか
      header: {
        left: '',
        center: 'title',
        right: ''
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
      // 予定の内容
      events: [
        { resourceId: '1', title: 'care1', start: '2019-10-31T08:00', end: '2019-10-31T08:45' },
        { resourceId: '1', title: 'care1', start: '2019-10-31T09:00', end: '2019-10-31T09:30' },
        { resourceId: '1', title: 'care1', start: '2019-10-31T10:00', end: '2019-10-31T11:00' },
        { resourceId: '1', title: 'care1', start: '2019-10-31T11:30', end: '2019-10-31T14:00' },
        { resourceId: '1', title: 'care1', start: '2019-10-31T14:30', end: '2019-10-31T16:00' },
        { resourceId: '1', title: 'care1', start: '2019-10-31T16:30', end: '2019-10-31T17:30' },
        { resourceId: '1', title: 'care1', start: '2019-10-31T18:00', end: '2019-10-31T19:30' },
        { resourceId: '1', title: 'care1', start: '2019-10-31T20:00', end: '2019-10-31T21:45' },
        { resourceId: '1', title: 'care1', start: '2019-10-31T22:15', end: '2019-10-31T23:00' },
        { resourceId: '1', title: 'care1', start: '2019-10-31T23:30', end: '2019-10-31T24:00' }
      ],
      buttonText: {
        today: '今日',
        month: '月',
        week: '週',
        day: '日'
      },
      config: {
        timeFormat: 'HH:mm',
        slotLabelFormat: 'HH:mm',
        slotDuration: '00:15:00',
        snapDuration: '01:00:00',
        displayEventTime: 'true',
        displayEventEnd: 'true',
        datesAboveResources: 'true',
        weekends: 'true',
        weekNumbers: 'true',

        eventRender (event, element) {
          return vm.eventFilter(event, element)
        }
      },
      eventFilter: (evt, el) => true
    }
  },

  watch: {
    eventFilter () {
      this.$refs.calendar.fireMetod('renderEvents')
    }
  }
}

</script>

<template>
  <div id="scroll">
    <!-- tooltipのテスト導入 -->
    <button v-tooltip="'TOPにメッセージが表示されます'">TOP</button>
    <!-- 表示確認用テキスト -->
    <h1>Calendar view test page</h1>
    <!-- export default > data > 各項目を設定、デフォルトから上書き -->
    <div id="fullcalendar">
      <div id="float_box">
        <FullCalendar
          schedulerLicenseKey="GPL-My-Project-Is-Open-Source"
          locale="ja"
          defaultView="resourceTimeGridDay"
          :config="config"
          :plugins="calendarPlugins"
          :header="header"
          :resources="resources"
          :events="events"
          :selectable="true"
          :editable="true"
          :buttonText="buttonText"
        />
      </div>
      <div id="float_box">
        <FullCalendar
          schedulerLicenseKey="GPL-My-Project-Is-Open-Source"
          locale="ja"
          defaultView="resourceTimeGridDay"
          :config="config"
          :plugins="calendarPlugins"
          :header="header"
          :resources="resources"
          :events="events"
          :selectable="true"
          :editable="true"
          :buttonText="buttonText"
        />
        <div></div>
      </div>
      <div id="float_box">
        <FullCalendar
          schedulerLicenseKey="GPL-My-Project-Is-Open-Source"
          locale="ja"
          defaultView="resourceTimeGridDay"
          :config="config"
          :plugins="calendarPlugins"
          :header="header"
          :resources="resources"
          :events="events"
          :selectable="true"
          :editable="true"
          :buttonText="buttonText"
        />
        <div></div>
      </div>
      <div id="float_box">
        <FullCalendar
          schedulerLicenseKey="GPL-My-Project-Is-Open-Source"
          locale="ja"
          defaultView="resourceTimeGridDay"
          :config="config"
          :plugins="calendarPlugins"
          :header="header"
          :resources="resources"
          :events="events"
          :selectable="true"
          :editable="true"
          :buttonText="buttonText"
        />
        <div></div>
      </div>
      <div id="float_box">
        <FullCalendar
          schedulerLicenseKey="GPL-My-Project-Is-Open-Source"
          locale="ja"
          defaultView="resourceTimeGridDay"
          :config="config"
          :plugins="calendarPlugins"
          :header="header"
          :resources="resources"
          :events="events"
          :selectable="true"
          :editable="true"
          :buttonText="buttonText"
        />
        <div></div>
      </div>
      <div id="float_box">
        <FullCalendar
          schedulerLicenseKey="GPL-My-Project-Is-Open-Source"
          locale="ja"
          defaultView="resourceTimeGridDay"
          :config="config"
          :plugins="calendarPlugins"
          :header="header"
          :resources="resources"
          :events="events"
          :selectable="true"
          :editable="true"
          :buttonText="buttonText"
        />
        <div></div>
      </div>
    </div>
  </div>
</template>

<style lang='scss'>

@import '~@fullcalendar/core/main.css';
@import '~@fullcalendar/daygrid/main.css';
@import '~@fullcalendar/timegrid/main.css';
@import '~@fullcalendar/resource-timeline/main.css';

// 土日の色付け
.fc-sun {
    color: red;
    background-color: #fff0f0;
}

/* 土曜日 */
.fc-sat {
    color: blue;
    background-color: #f0f0ff;
}

#scroll {
  overflow-x: scroll;
  width: auto;
}

#fullcalendar {
  display: inline-block;
  white-space: nowrap;
}

#float_box {
  display: inline-block;
  width: 500px;
  margin: 10px;
  display:inline-block;
}

</style>
