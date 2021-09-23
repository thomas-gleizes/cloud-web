<script>

import moment from "moment";

export default {
  name: "TimeTo",
  props: {
    limitDate: {
      type: Date,
      required: true
    }
  },
  methods: {
    singleDigit: (value) => `0${value}`.slice(-2),
    getS: (value) => value && value.length >= 1 ? "s" : "",
    format: (date) => moment(date).format('DD/MM/YYYY'),
    getInterval: (time, timestamp) => time + timestamp,
  },
  data() {
    return {
      interval: null,
      days: (this.limitDate),
      hours: 20,
      minutes: 10,
      secondes: 20
    };
  },
  mounted() {
    this.interval = setInterval(() => {

    }, 1000)
  }
};
</script>

<template>
  <div class="">
    Limit date : {{ format(this.limitDate) }}
  </div>
  <div class="flex justify-center">
    <div class="mx-1">{{ days }} jours</div>
    <div class="mx-1">{{ hours }} heurs</div>
    <div class="mx-1">{{ minutes }} minutes</div>
    <div class="mx-1">{{ secondes }} secondes</div>
  </div>
</template>
