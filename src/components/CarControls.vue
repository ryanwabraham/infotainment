<template>
  <div class="column">
    <div class="button-wrapper">
      <Button icon="music" />
      <Button icon="phone" />
      <Button icon="web" />
      <Button icon="windshield--washer" />
      <Button icon="hazard" />
      <Button
        icon="palette animate__wobble"
        v-on:click.native="showThemePicker"
      />
    </div>
    <TemperatureControls />
    <Music />
  </div>
</template>

<script>
import Button from "./Button.vue";
import TemperatureControls from "./TemperatureControls.vue";
import Music from "./Music.vue";

export default {
  name: "CarControls",
  components: {
    Button,
    TemperatureControls,
    Music
  },
  methods: {
    showThemePicker: () => {
      const themePicker = document.getElementById("theme-picker");
      themePicker.classList.toggle("open");
    }
  }
};
</script>

<style scoped lang="scss">
.button-wrapper {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;

  .button {
    width: calc(33.33% - 55px);
    margin-bottom: 20px;
  }
}
</style>
