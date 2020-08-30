<template>
  <div id="app">
    <div class="calendarComponents">
      <Calendar v-bind:min-date="currentDate" v-bind:max-date="maxDate" v-on:dayclick="daychanged"/>
      <Timeselector/>
    </div>
  </div>
</template>

<script>
import Calendar from 'v-calendar/lib/components/calendar.umd'
import Timeselector from 'vue-timeselector';

export default {
  name: 'App',
  components: {
    Calendar,
    Timeselector
  },
  data() {
    var currentDate = new Date();
    var maxDate = new Date();
    maxDate.setDate(currentDate.getDate() + 14);
    return {
      currentDate: currentDate,
      maxDate: maxDate
    }
  },
  mounted() {
    //Vue devtools
    let devscript = document.createElement('script');
    devscript.setAttribute('src','http://localhost:8098');
    document.head.appendChild(devscript);
  },
  methods: {
    daychanged: function(event) {
      console.log(event);
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  width: 30%;
}
.calendarComponents{
  width: 50%;
  background-color: cornflower-blue;

}
</style>
