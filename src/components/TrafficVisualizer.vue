<template>
  <div class="traffic-visualizer">
    <div class="lane-lines"></div>
    <div class="car"></div>
    <div class="lane-lines"></div>
  </div>
</template>

<script>
export default {
  name: "TrafficVisualizer"
};
</script>

<style scoped lang="scss">
.traffic-visualizer {
  position: absolute;
  width: 100%;
  top: 220px;
  left: 0;
  bottom: 145px;
  display: flex;
  align-items: center;
  justify-content: center;
  overflow: hidden;

  &::before,
  &::after {
    position: absolute;
    display: block;
    content: "";
    width: 100%;
    height: 50px;
  }

  &::before {
    top: 0;
    background: rgb(255, 255, 255);
    background: linear-gradient(
      180deg,
      rgba(255, 255, 255, 1) 0%,
      rgba(255, 255, 255, 0) 100%
    );
    z-index: 1;
  }

  &::after {
    bottom: 0;
    background: rgb(255, 255, 255);
    background: linear-gradient(
      0deg,
      rgba(255, 255, 255, 1) 0%,
      rgba(255, 255, 255, 0) 100%
    );
  }
}

.lane-lines {
  height: 70%;
  width: 4px;
  position: relative;
  animation: passingLanes 0.25s linear infinite;
  border-radius: 5px;
  margin: 0px 40px;
  background: var(--color-accent);
}

.car {
  width: 28%;
  height: 100%;
  background-image: url("../assets/car--white.png");
  background-position: center center;
  background-size: contain;
  background-repeat: no-repeat;
  animation: sway 8s ease-in-out infinite;
}

@keyframes passingLanes {
  0% {
    top: -100%;
  }
  100% {
    top: 100%;
  }
}

@keyframes sway {
  0% {
    transform: translateX(0);
  }
  40% {
    transform: translateX(30px);
  }
  75% {
    transform: translateX(-20px);
  }
  100% {
    transform: translateX(0);
  }
}

#app[data-theme="dark"] .traffic-visualizer {
  &::before {
    background: rgb(50, 71, 107);
    background: linear-gradient(
      180deg,
      rgba(44, 62, 95, 1) 0%,
      rgba(44, 62, 95, 0) 100%
    );
  }

  &::after {
    background: rgb(29, 32, 53);
    background: linear-gradient(
      0deg,
      rgba(44, 62, 95, 1) 0%,
      rgba(44, 62, 95, 0) 100%
    );
  }

  .car {
    background-image: url("../assets/car--dark.png");
    background-position: center center;
    background-size: contain;
  }
}

#app[data-theme="cyberpunk"] .traffic-visualizer {
  &::before {
    background: rgb(29, 32, 53);
    background: linear-gradient(
      180deg,
      rgba(29, 32, 53, 1) 0%,
      rgba(29, 32, 53, 0) 100%
    );
  }

  &::after {
    background: rgb(29, 32, 53);
    background: linear-gradient(
      0deg,
      rgba(29, 32, 53, 1) 0%,
      rgba(29, 32, 53, 0) 100%
    );
  }

  .lane-lines {
    box-shadow: 0px 0px 10px 0px rgba(255, 68, 133, 1);
  }

  .car {
    background-image: url("../assets/car--cyberpunk.png");
    background-position: center center;
    background-size: contain;
  }
}
</style>
