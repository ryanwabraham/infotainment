<template>
  <div class="card temperature">
    <div class="slider-wrapper">
      <Slider :min="10" :max="30" :default="21" units="°C" icon="temperature" />
      <Slider :min="0" :max="10" :default="1" units=" " icon="fan" />
      <Slider :min="20" :max="45" :default="25" units="°C" icon="seat-heater" />
      <Slider
        :min="0"
        :max="10"
        :default="10"
        units=" "
        icon="windshield--defroster"
      />
      <Slider
        :min="0"
        :max="10"
        :default="7"
        units=" "
        icon="windshield--wiper"
      />
    </div>
  </div>
</template>

<script>
import Slider from "./Slider.vue";
export default {
  name: "TemperatureControls",
  components: {
    Slider
  }
};
</script>

<style scoped lang="scss">
.temperature {
  flex: 1;
  margin-bottom: 20px;
}

.slider-wrapper {
  display: flex;
  justify-content: space-between;
  padding: 0px calc(16.66% - 34px); // align to button icons
  height: 100%;
}
</style>
