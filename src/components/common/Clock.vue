<script>
export default {
  name: "Clock",
  data() {
    const time = new Date();

    return {
      interval: null,
      hours: time.getHours(),
      minutes: time.getMinutes(),
      secondes: time.getSeconds(),
    };
  },
  mounted() {
    this.interval = setInterval(() => {
      const time = new Date();

      this.hours = time.getHours();
      this.minutes = time.getMinutes();
      this.secondes = time.getSeconds();
    }, 1000);
  },
  unmounted() {
    clearInterval(this.interval);
  },
  methods: {
    singleDigit: (digit) => `0${digit}`.slice(-2),
  },
};
</script>

<template>
  <div>
    <span>{{ singleDigit(hours) }} : {{ singleDigit(minutes) }} : {{ singleDigit(secondes) }} </span>
  </div>
</template>
