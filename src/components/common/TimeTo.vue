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
    this.interval = setInterval(() => {
      let diff = Math.floor((this.limitDate.getTime() - Date.now()) / 1000);
      this.timestampDiff = diff;

      this.days = Math.floor(diff / DAY);
      diff -= Math.floor(Math.floor((diff / DAY)));
      this.hours = Math.floor(Math.floor(diff / HOUR) * 24 / 100);
      diff -= Math.floor(diff / HOUR);
      this.minutes = Math.floor(Math.floor(diff / MINUTE) * 60 / 100);
      diff -= Math.floor(diff / MINUTE);
      this.secondes = Math.floor(Math.floor(diff / SECOND) * 60 / 100);
    }, 100);
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
