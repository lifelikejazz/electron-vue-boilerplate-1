<template>
  <div class="clock">
    <h1>{{ time }}</h1>
  </div>
</template>

<script>
  export default {
    data () {
      return { time: "00:00:00" }
    },
    mounted () {
      this.startTime();
    },
    methods: {
      startTime () {
        let today = new Date();
        let h = today.getHours();
        let m = today.getMinutes();
        let s = today.getSeconds();
        m = this.checkTime(m);
        s = this.checkTime(s);

        this.time = h + ":" + m + ":" + s;
        let t = setTimeout(this.startTime, 500);
      },
      checkTime (i) {
        if (i < 10) {i = "0" + i};
        return i;
      }
    }
  }
</script>

<style>
  .clock {
    color: #C03763;
    font-size: 48px;
    line-height: 1.1em;
    margin: 40px 0 60px;
  }
</style>
