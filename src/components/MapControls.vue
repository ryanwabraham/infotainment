<template>
  <div class="column">
    <div class="card map"></div>
    <div class="card directions">
      <div class="icon right-turn"></div>
      <h3>
        Turn right onto Moray St.
        <br />
        <span class="directions__distance">0.25 km</span>
      </h3>
    </div>
  </div>
</template>

<script>
export default {
  name: "MapControls"
};
</script>

<style scoped lang="scss">
.card.map {
  padding: 0px;
  overflow: hidden;
  flex: 1;
  margin-bottom: 20px;
  background-image: url(../assets/map.png);
  background-repeat: no-repeat;
  background-size: cover;
  background-position: center center;

  img {
    width: 100%;
    height: 100%;
  }
}

.card.directions {
  padding: 0px;
  display: flex;
}

.icon.right-turn {
  width: calc(33.33% - 15px);
  height: 100%;
  background-size: 25px 25px;
}

h3 {
  line-height: 1.5;
  white-space: nowrap;
  overflow-x: hidden;
  text-overflow: ellipsis;
  margin-right: 1em;
  color: var(--color-text-accent);
}

.directions__distance {
  color: var(--color-text);
}

#app[data-theme="dark"] .card.map {
  background-image: url(../assets/map--dark.png);
  background-size: cover;
}

#app[data-theme="cyberpunk"] .card.map {
  background-image: url(../assets/map--cyberpunk.png);
  background-size: cover;
}
</style>
