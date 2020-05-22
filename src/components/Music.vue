<template>
  <div class="card music">
    <div class="icon pause"></div>
    <div class="music__title">
      <h3>
        Blade Runner Blues
        <br />
        <span class="music__artist">Vangelis • 1982</span>
      </h3>
    </div>
    <div class="music__thumbnail"></div>
  </div>
</template>

<script>
export default {
  name: "Music"
};
</script>

<style scoped lang="scss">
.card.music {
  padding: 0px;
  display: flex;
}

h3 {
  color: var(--color-text-accent);
  line-height: 1.5;
}

.music__artist {
  margin: 0px;
  color: var(--color-text);
  white-space: nowrap;
  overflow-x: hidden;
  text-overflow: ellipsis;
}

.icon.pause {
  width: calc(33.33% - 15px);
  height: 100%;
  background-size: 30px 30px;
}
</style>
