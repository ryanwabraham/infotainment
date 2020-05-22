<template>
  <div class="slider">
    <vue-slider
      :value="value"
      :tooltip-formatter="formatter"
      :height="150"
      :tooltip-placement="'top'"
      :min="min"
      :max="max"
      :interval="1"
      direction="btt"
    ></vue-slider>
    <div :class="['icon', icon]"></div>
  </div>
</template>

<script>
import VueSlider from "vue-slider-component";
import "vue-slider-component/theme/default.css";

export default {
  name: "Slider",
  props: {
    min: Number,
    max: Number,
    default: Number,
    units: String,
    icon: String
  },
  components: {
    VueSlider
  },
  data: function() {
    return {
      value: this.default,
      formatter: `{value}${this.units}`
    };
  }
};
</script>

<style lang="scss">
.slider {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: space-evenly;

  .vue-slider-rail {
    background-color: var(--color-bg);
  }

  .vue-slider-process {
    background-color: var(--color-accent);
  }

  .vue-slider-dot-tooltip-inner {
    border-color: var(--color-accent);
    background: var(--color-accent);
  }

  .icon {
    margin: 20px 0px 0px 0px;
    width: 25px;
    height: 25px;
    background-size: 25px 25px;

    &.windshield--wiper {
      width: 27px;
      height: 27px;
      background-size: 27px 27px;
    }
  }
}

#app[data-theme="dark"] .slider,
#app[data-theme="cyberpunk"] .slider {
  .vue-slider-dot-handle {
    background: var(--color-text);
  }

  .vue-slider-process {
    background: var(--color-text);
  }
}

#app[data-theme="cyberpunk"] .slider {
  .vue-slider-process {
    background: var(--color-accent);
    box-shadow: 0px 0px 10px 0px rgba(255, 68, 133, 1);
  }

  .vue-slider-dot-tooltip-inner-top::after {
    display: none;
  }
}
</style>
