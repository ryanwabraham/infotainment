<template>
  <div id="app" data-theme="dark">
    <main>
      <MobileDisclaimer />
      <ThemePicker />
      <DriveControls />
      <CarControls />
      <MapControls />
    </main>
  </div>
</template>

<script>
import MobileDisclaimer from "./components/MobileDisclaimer.vue";
import ThemePicker from "./components/ThemePicker.vue";
import DriveControls from "./components/DriveControls.vue";
import CarControls from "./components/CarControls.vue";
import MapControls from "./components/MapControls.vue";

export default {
  name: "app",
  components: {
    MobileDisclaimer,
    ThemePicker,
    DriveControls,
    CarControls,
    MapControls
  }
};
</script>

<style lang="scss">
@import "./styles/_main.scss";
@import "./styles/_icons.scss";
</style>
