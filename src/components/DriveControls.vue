<template>
  <div id="drive-controls" class="column card">
    <StatusBar />
    <Speedometer />
    <TrafficVisualizer />
    <Gear />
    <Range />
  </div>
</template>

<script>
import StatusBar from "./StatusBar.vue";
import Speedometer from "./Speedometer.vue";
import TrafficVisualizer from "./TrafficVisualizer.vue";
import Gear from "./Gear.vue";
import Range from "./Range.vue";

export default {
  name: "DriveControls",
  components: {
    StatusBar,
    Speedometer,
    TrafficVisualizer,
    Gear,
    Range
  }
};
</script>

<style scoped lang="scss">
#drive-controls {
  padding: 0px;
}
</style>
