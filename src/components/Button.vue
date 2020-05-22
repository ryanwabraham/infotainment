<template>
  <div
    class="card button"
    v-bind:class="{ active: isActive }"
    v-on:click="isActive = !isActive"
  >
    <div :class="['icon', icon]"></div>
  </div>
</template>

<script>
export default {
  name: "Button",
  props: {
    icon: String
  },
  data: function() {
    return {
      isActive: false
    };
  }
};
</script>

<style scoped lang="scss">
.button {
  display: flex;
  align-items: center;
  justify-content: center;
  cursor: pointer;

  &:after {
    content: "";
    display: block;
    padding-bottom: 100%;
  }

  &.active {
    background-color: var(--color-accent);

    .icon {
      &.hazard {
        background-image: url(../assets/hazard--active.png);
      }

      &.music {
        background-image: url(../assets/music--active.png);
      }

      &.phone {
        background-image: url(../assets/phone--active.png);
      }

      &.web {
        background-image: url(../assets/web--active.png);
      }

      &.windshield--washer {
        background-image: url(../assets/windshield--washer--active.png);
      }
    }
  }

  .icon {
    width: 25px;
    height: 25px;
    background-size: 25px 25px;

    &.windshield--washer {
      width: 28px;
      height: 28px;
      background-size: 28px 28px;
    }
  }
}

#app[data-theme="cyberpunk"] .card.active {
  background: var(--color-accent);
  border: 2px solid transparent;
}

.animate__wobble {
  animation: wobble 2s linear infinite;
}

@keyframes wobble {
  from {
    transform: translate3d(0, 0, 0);
  }
  5% {
    transform: translate3d(-25%, 0, 0) rotate3d(0, 0, 1, -5deg);
  }
  15% {
    transform: translate3d(20%, 0, 0) rotate3d(0, 0, 1, 3deg);
  }
  25% {
    transform: translate3d(-15%, 0, 0) rotate3d(0, 0, 1, -3deg);
  }
  35% {
    transform: translate3d(10%, 0, 0) rotate3d(0, 0, 1, 2deg);
  }
  45% {
    transform: translate3d(-5%, 0, 0) rotate3d(0, 0, 1, -1deg);
  }
  50% {
    transform: translate3d(0, 0, 0);
  }
}
</style>
