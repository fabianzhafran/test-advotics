<template>
  <div>
    <Navbar />
    <div class="content">
      <Sidebar />
      <div class="dashboard">
        <div class="top-row">
          <h1>Dashboard</h1>
          <div class="calendar-button">
            <img src="../assets/img/calendar.png" class="calendar-icon">
            <span>Period</span>
            <span>{{startDate}} - {{endDate}}</span>
            <b-button 
              v-b-popover.click.blur.bottomleft.html="calendarPopup"
              class="drop-down-icon drop-down-button">
              <img src="../assets/img/drop-down.png" class="drop-down-icon">
            </b-button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Navbar from '../modules/components/Navbar.vue'
import Sidebar from '../modules/components/Sidebar.vue'

export default {
  name: 'Home',
  components: {
    Navbar,
    Sidebar
  },
  data() {
    return {
      startDate: '-',
      endDate: '-'
    }
  }
}
</script>

<style scoped>
.content {
  display: flex;
  flex-direction: row;
  min-height: 90vh;
  width: 100%;
}

.dashboard {
  padding: 50px;
  width: 100%;
}

h1 {
  color:#707070C4;
}

.top-row {
  display: flex;
  justify-content: space-between;
}

.calendar-button {
  box-shadow: 0px 2px 3px #00000029;
  width: 40vw;
  height: 60px;
  display: flex;
  align-items: center;
  padding: 20px;
}

.calendar-button > span {
  margin: 0 20px;
}

.drop-down-button {
  background: none !important;
  border: 0px white !important;
  border-radius: 0px;
  transition: none;
  height: 100%;
}

.drop-down-button:focus {
  border: 2px white !important;
}

.drop-down-icon {
  margin-left: auto;
  height: 130%;
}
</style>
