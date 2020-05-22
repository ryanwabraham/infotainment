<template>
  <div class="range">
    <h3>{{ range }} km</h3>
    <h3>
      {{ batteryLevel }}%
      <div class="icon battery"></div>
    </h3>
  </div>
</template>

<script>
export default {
  name: "Range",
  data: () => {
    return {
      range: 235,
      batteryLevel: 91
    };
  },
  methods: {
    decrementBattery() {
      this.range -= 5;
      this.batteryLevel -= 1;
    }
  },
  mounted() {
    this.interval = setInterval(this.decrementBattery, 20000);
  },
  beforeDestroy() {
    clearInterval(this.interval);
  }
};
</script>

<style scoped lang="scss">
.range {
  position: absolute;
  left: 20px;
  right: 20px;
  bottom: 20px;
  display: flex;
  align-items: center;
  justify-content: space-between;

  h3 {
    display: flex;
    margin: 0px;
    color: var(--color-text-accent);
  }

  .battery {
    margin-left: 5px;
    transform: rotate(90deg);
  }
}

#app[data-theme="dark"] h3,
#app[data-theme="cyberpunk"] h3 {
  color: var(--color-text);
}
</style>
