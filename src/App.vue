<template>
  <div id="app" data-theme="dark">
    <main>
      <ThemePicker />
      <DriveControls />
      <CarControls />
      <MapControls />
    </main>
  </div>
</template>

<script>
import ThemePicker from "./components/ThemePicker.vue";
import DriveControls from "./components/DriveControls.vue";
import CarControls from "./components/CarControls.vue";
import MapControls from "./components/MapControls.vue";

export default {
  name: "app",
  components: {
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
