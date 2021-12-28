<template>
  <div class="calendar-month-name">{{ selectedMonth }}</div>
</template>

<script>
export default {
  props: {
    selectedDate: {
      type: Object,
      required: true
    }
  },

  computed: {
    selectedMonth() {
      return this.selectedDate.format("MMMM YYYY");
    }
  }
};
</script>

<style scoped>
.calendar-month-name {
  font-size: 0.8rem;
  font-weight: 600;
  color: var(--grey-00);
}
</style>

