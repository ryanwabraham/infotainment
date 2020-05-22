<template>
  <div class="statusbar">
    <div class="statusbar__icons">
      <div class="icon lte" title="LTE"></div>
      <div class="icon wifi" title="WiFi"></div>
      <div class="icon bluetooth" title="Bluetooth"></div>
    </div>
    <h3>{{ dateNow }}</h3>
  </div>
</template>

<script>
export default {
  name: "StatusBar",
  data: () => {
    return {
      dateNow: ""
    };
  },
  methods: {
    time() {
      const date = new Date();
      let amPm;
      let hour = date.getHours();
      let minutes = date.getMinutes();
      if (hour > 12) {
        hour -= 12;
        amPm = "pm";
      } else {
        amPm = "am";
      }
      if (minutes < 10) minutes = `0${minutes}`;
      this.dateNow = `${hour}:${minutes}${amPm}`;
    }
  },
  created() {
    this.time();
  },
  mounted() {
    this.interval = setInterval(this.time, 60000);
  },
  beforeDestroy() {
    clearInterval(this.interval);
  }
};
</script>

<style scoped lang="scss">
.statusbar {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 20px;

  .statusbar__icons {
    display: flex;

    .icon {
      margin-right: 10px;
    }
  }

  h3 {
    margin: 0px;
    color: var(--color-text-accent);
  }
}

#app[data-theme="dark"] h3,
#app[data-theme="cyberpunk"] h3 {
  color: var(--color-text);
}
</style>
