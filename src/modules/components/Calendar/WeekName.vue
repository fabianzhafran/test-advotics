<template>
  <ol class="day-of-week">
    <li v-for="weekday in weekdays" :key="weekday">{{ weekday }}</li>
  </ol>
</template>

<script>
const WEEKDAYS = ["Mon", "Tue", "Wed", "Thu", "Fri", "Sat", "Sun"];

export default {
  name: "CalendarWeekdays",

  computed: {
    weekdays() {
      return WEEKDAYS;
    }
  }
};
</script>

<style scoped>
ol li {
  list-style: none !important;
  border-bottom: 0.5px solid #D2D2D2;
}

.week-name {
  display: grid;
  grid-template-columns: repeat(7, 1fr);
}

.week-name > * {
  text-align: right;
  padding-right: 5px;
}
</style>
