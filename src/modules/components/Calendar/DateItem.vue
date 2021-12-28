<template>
  <li
    class="calendar-day"
    :class="{
      'calendar-day-green': green
    }"
  >
    <span>{{ label }}</span>
  </li>
</template>

<script>
import dayjs from "dayjs";

export default {
  name: "DateItem",

  props: {
    day: {
      type: Object,
      required: true
    },

    isCurrentMonth: {
      type: Boolean,
      default: false
    },

    green: {
      type: Boolean,
      default: false
    }
  },

  computed: {
    label() {
      return this.day.isCurrentMonth ? dayjs(this.day.date).format("D") : '';
    }
  }
};
</script>

<style scoped>
li {
  list-style: none !important;
  padding: 0;
}

li span {
  text-align: center;

}

.calendar-day {
  position: relative;
  min-height: 30px;
  font-size: 0.7rem;
  background-color: #fff;
  color: var(--grey-800);
}

.calendar-day > span {
  display: flex;
  justify-content: center;
  align-items: center;
  position: absolute;
  right: 2px;
}

.calendar-day-green {
  background-color: #37B04C;
}

.calendar-day-green > span {
  color: #fff;
  border-radius: 9999px;
}
</style>
