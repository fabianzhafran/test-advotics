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
              id="calendar-popover"
              class="drop-down-icon drop-down-button">
              <img src="../assets/img/drop-down.png" class="drop-down-icon" @click="onClickCalendar">
            </b-button>
            <b-popover
              ref="popover"
              target="calendar-popover"
              placement="bottomleft"
              class="popover"
              blur
            >
              <div class="top-calendar-bar">
                <button
                  @click="closePopover"
                  class="close-popover-button"
                >
                  ✕
                </button>
              </div>
              <div class="calendar-wrapper">
                <div class="interval-wrapper">
                  <div class="intervals">
                    <p v-for="item in intervals" 
                      :key="item"
                      :class="item == chosenInterval ? 'green interval' : 'interval'"
                      @click="setInterval(item)"
                    >
                      {{ item }}
                    </p>
                    <b-form-input v-model="startDateVar" placeholder="Start Date" size="sm"></b-form-input>
                    <b-form-input v-model="endDateVar" placeholder="End Date" size="sm"></b-form-input>
                    <b-button class="apply-button" variant="success" @click="onClickApply">Apply</b-button>
                  </div>
                </div>
                <CalendarMonth :startDate="startDateJs" :endDate="endDateJs" :checkMore="false" :calculateDateDifference="calculateDateDifference"/>
                <CalendarMonth :startDate="startDateJs" :endDate="endDateJs" :checkMore="true" :calculateDateDifference="calculateDateDifference"/>
              </div>

            </b-popover>
          </div>
        </div>
        <div class="market-insight">
          <h3>MARKET INSIGHT</h3>
        </div>
        <div class="sales-turnover">

        </div>
        
      </div>
    </div>
  </div>
</template>

<script>
import Navbar from '../modules/components/Navbar.vue'
import Sidebar from '../modules/components/Sidebar.vue'
import CalendarMonth from '../modules/components/Calendar/CalendarMonth.vue'

import dayjs from "dayjs";

export default {
  name: 'Home',
  components: {
    Navbar,
    Sidebar,
    CalendarMonth
  },
  data() {
    return {
      startDate: 'Start Date',
      endDate: 'End Date',
      startDateVar: '',
      endDateVar: '',
      startDateJs: dayjs(),
      endDateJs: dayjs(),

      intervals: [
        'Yesterday',
        'Last 7 Days',
        'Last 30 Days',
        'This Month',
        'Custom'
      ],
      chosenInterval: ''
    }
  },
  methods: {
    setInterval(interval) {
      this.chosenInterval = interval
    },
    onClickCalendar() {

    },
    closePopover() {
      this.$refs.popover.$emit('close')
    },
    onClickApply() {
      let invalidDate = false;
      if (this.chosenInterval === 'Yesterday') {
        this.startDateJs = dayjs().subtract(1, "day")
        this.endDateJs = dayjs().subtract(1, "day")
      } else if (this.chosenInterval === 'Last 7 Days') {
        this.startDateJs = dayjs().subtract(7, "day")
        this.endDateJs = dayjs().subtract(1, "day")
      } else if (this.chosenInterval === 'Last 30 Days') {
        this.startDateJs = dayjs().subtract(30, "day")
        this.endDateJs = dayjs().subtract(1, "day")
      } else if (this.chosenInterval === 'This Month') {
        this.startDateJs = dayjs().date(1)
        this.endDateJs = dayjs()
      } else if (this.chosenInterval === 'Custom') {
        this.startDateJs = dayjs(this.startDateVar)
        this.endDateJs = dayjs(this.endDateVar)
        let difference = this.calculateDateDifference(this.endDateJs, this.startDateJs)
        let diffStartToday = this.calculateDateDifference(dayjs(), this.startDateJs)
        let diffEndToday = this.calculateDateDifference(dayjs(), this.endDateJs)
        console.log(difference)

        if (difference > 180 || difference < 0 || diffStartToday < 0 || diffEndToday < 0) {
          invalidDate = true
        }
      }
      
      if (!invalidDate) {
        this.startDate = this.startDateJs.format().split('T')[0]
        this.endDate = this.endDateJs.format().split('T')[0]
      }
    },
    calculateDateDifference(dateA, dateB) {
      let yearDiff = (parseInt(dateA.format().split('T')[0].split('-')[0]) - parseInt(dateB.format().split('T')[0].split('-')[0])) * 365
      let monthDiff = (parseInt(dateA.format().split('T')[0].split('-')[1]) - parseInt(dateB.format().split('T')[0].split('-')[1])) * 30
      let dayDiff = (parseInt(dateA.format().split('T')[0].split('-')[2]) - parseInt(dateB.format().split('T')[0].split('-')[2]))
      return yearDiff + monthDiff + dayDiff
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

.popover {
  min-width: 750px !important;
  min-height: 480px !important;
}

.top-calendar-bar {
  display: flex;
  justify-content: flex-end;
  margin-bottom: 10px;
}

.close-popover-button {
  background: none;
  border: none;
  font-size: 1.5rem;
  font-weight: bold;
}

.calendar-wrapper {
  display: flex;
  flex-direction: row;
}

.interval-wrapper {
  flex: 1;
  border-right: 0.5px solid #D2D2D2;
  padding: 0 20px 0 10px;
}

.green {
  border-radius: 3px;
  border: none !important;
  color: white !important;
  background-color: #37B04C;
  font-weight: bold;
}

.intervals {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}

.interval {
  border-bottom: 0.5px solid #D2D2D2;
  padding-bottom: 5px;
  color: #8B8B8B;
}

.apply-button {
  margin-top: 10px;
}
</style>
