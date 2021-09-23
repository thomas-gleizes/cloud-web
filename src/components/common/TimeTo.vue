<script>

import moment from "moment";
import Clock from "@/components/common/Clock";

const SECOND = 1;
const MINUTE = SECOND * 60;
const HOUR = MINUTE * 60;
const DAY = HOUR * 24;

export default {
  name: "TimeTo",
  components: { Clock },
  props: {
    limitDate: {
      type: Date,
      required: true
    }
  },
  methods: {
    decreaseTimer () {
      let diff = Math.floor((this.limitDate.getTime() - Date.now()) / 1000);
      this.timestampDiff = diff;

      this.days = Math.floor(diff / DAY);
      diff -= this.days * DAY;
      this.hours = Math.floor(diff / HOUR);
      diff -= this.hours * HOUR;
      this.minutes = Math.floor(diff / MINUTE);
      diff -= this.minutes * MINUTE;
      this.secondes = Math.floor(diff / SECOND)
    },
    singleDigit: (value) => `0${value}`.slice(-2),
    format: (date) => moment(date).format("DD/MM/YYYY")
  },
  data() {
    return {
      interval: null,
      days: 0,
      hours: 0,
      minutes: 0,
      secondes: 0,
      timestampDiff: 0
    };
  },
  mounted() {
    this.decreaseTimer()
    this.interval = setInterval(this.decreaseTimer, 100);
  },
  unmounted() {
    clearInterval(this.interval);
  }
};
</script>

<template>
  <div class="">
    Limit date : {{ format(this.limitDate) }}
  </div>
  <div>
    Timestamp : {{ timestampDiff }}
  </div>
  <div class="flex justify-center">
    <div class="mx-1">{{ days }} jours</div>
    <div class="mx-1">{{ singleDigit(hours) }} heurs</div>
    <div class="mx-1">{{ singleDigit(minutes) }} minutes</div>
    <div class="mx-1">{{ singleDigit(secondes) }} secondes</div>
  </div>
  <div class="text-center">
    {{ format(new Date()) }}
    <Clock />
  </div>
</template>
