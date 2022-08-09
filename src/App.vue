<template>
<div id='app'>
  <ejs-schedule height="550px" :selectedDate="schedulerSelectedDate"
  :eventSettings="appointmentData">
  </ejs-schedule>
</div>
</template>

<script> 
import { ScheduleComponent, Day, Week, WorkWeek, 
Month, Agenda } from "@syncfusion/ej2-vue-schedule";

export default {
  name: 'App',
  components: {
    'ejs-schedule': ScheduleComponent
  },
  provide : {
    schedule : [Day, Week, WorkWeek, Month, Agenda]
  },
  data() {
    return {
      schedulerSelectedDate : new Date(2022, 4, 12),
      appointmentData : {
        enableTooltip : true,
        fields : {
          subject : { name : 'Summary', title : 'Event'},
          startTime : { name : 'Start', title : 'Event StartTime'},
          endTime : { name : 'End', title : 'Event EndTime'}
        },
        dataSource : [
          {
            Summary : 'Review Meeting',
            Start : new Date(2022, 4, 11, 10, 0),
            End : new Date(2022, 4, 11, 12, 0)
          }
           // {
          //   Subject : 'Scrum Meeting',
          //   StartTime: new Date(2022, 4, 9, 9, 0),
          //   EndTime: new Date(2022, 4, 9, 10, 0),
          //   RecurrenceRule : "FREQ=DAILY;INTERVAL=1;COUNT=10"
          // },
          // {
          //   Subject : 'Demo Meeting',
          //   StartTime: new Date(2022, 4, 10, 10, 30),
          //   EndTime: new Date(2022, 4, 10, 12, 0),
          //   IsReadonly : true
          // },
          // {
          //   Subject : 'Testing',
          //   StartTime: new Date(2022, 4, 10, 13, 30),
          //   EndTime: new Date(2022, 4, 10, 14, 30),
          //   IsAllDay : true
          // },
          // {
          //   Subject : 'Core Team Meeting',
          //   StartTime: new Date(2022, 4, 12, 10, 0),
          //   EndTime: new Date(2022, 4, 12, 11, 0),
          //   IsBlock : true
          // },
          // {
          //   Subject : 'Project Discussion',
          //   StartTime: new Date(2022, 4, 13, 12, 0),
          //   EndTime: new Date(2022, 4, 13, 13, 0)
          // }
        ]
      }
    };
  },
}
</script>

<style>
@import '../node_modules/@syncfusion/ej2-base/styles/material.css';
@import '../node_modules/@syncfusion/ej2-buttons/styles/material.css';
@import '../node_modules/@syncfusion/ej2-calendars/styles/material.css';
@import '../node_modules/@syncfusion/ej2-dropdowns/styles/material.css';
@import '../node_modules/@syncfusion/ej2-inputs/styles/material.css';
@import '../node_modules/@syncfusion/ej2-navigations/styles/material.css';
@import '../node_modules/@syncfusion/ej2-popups/styles/material.css';
@import '../node_modules/@syncfusion/ej2-vue-schedule/styles/material.css';
</style>
