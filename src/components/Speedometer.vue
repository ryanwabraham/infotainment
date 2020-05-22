<template>
  <div class="speedometer">
    <div class="icon warning left"></div>
    <div class="icon warning right"></div>
    <h1>{{ speed }}</h1>
    <h3>kph</h3>
  </div>
</template>

<script>
export default {
  name: "Speedometer",
  data: () => {
    return {
      speed: 85
    };
  },
  methods: {
    updateSpeed() {
      let currentSpeed = this.speed;
      const random = Math.floor(Math.random() * 10);
      const diff = random > 5 ? 1 : -1;
      this.speed = currentSpeed + diff;
    }
  },
  mounted() {
    this.interval = setInterval(this.updateSpeed, 5000);
  },
  beforeDestroy() {
    clearInterval(this.interval);
  }
};
</script>

<style scoped lang="scss">
.speedometer {
  position: relative;
  text-align: center;

  h1,
  h3 {
    margin: 0;
  }

  h1 {
    font-size: 7rem;
    color: var(--color-text-accent);
  }

  .warning {
    position: absolute;
    top: 25%;
    width: 50px;
    height: 50px;
    margin: auto;
    background-size: contain;
    opacity: 0;

    &.left {
      left: 10%;
      animation: left-flasher 8s infinite;
    }

    &.right {
      right: 10%;
      animation: right-flasher 8s infinite;
    }
  }

  @keyframes left-flasher {
    from,
    67.5%,
    to {
      opacity: 0;
    }

    70%,
    72.5% {
      opacity: 1;
    }
    72.5%,
    75% {
      opacity: 0;
    }
    75%,
    77.5% {
      opacity: 1;
    }
    77.5%,
    80% {
      opacity: 0;
    }
    80%,
    82.5% {
      opacity: 1;
    }
    82.5%,
    85% {
      opacity: 0;
    }
    85%,
    87.5% {
      opacity: 1;
    }
    87.5%,
    100% {
      opacity: 0;
    }
  }
  @keyframes right-flasher {
    from,
    27.5%,
    to {
      opacity: 0;
    }

    30%,
    32.5% {
      opacity: 1;
    }
    32.5%,
    35% {
      opacity: 0;
    }
    35%,
    37.5% {
      opacity: 1;
    }
    37.5%,
    40% {
      opacity: 0;
    }
    40%,
    42.5% {
      opacity: 1;
    }
    42.5%,
    100% {
      opacity: 0;
    }
  }
}

#app[data-theme="cyberpunk"] .speedometer {
  h1 {
    text-shadow: 0 0 0.5rem var(--color-text-accent);
  }
}
</style>
