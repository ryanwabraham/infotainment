<template>
  <div class="gear">
    <h2>P</h2>
    <h2>R</h2>
    <h2 class="engaged">D</h2>
    <h2>N</h2>
  </div>
</template>

<script>
export default {
  name: "Gear"
};
</script>

<style scoped lang="scss">
.gear {
  display: flex;
  justify-content: center;
  align-items: center;
  position: absolute;
  bottom: 40px;
  left: 20px;
  right: 20px;

  h2 {
    margin-right: 20px;
    color: var(--color-text);

    &.engaged {
      font-size: 3rem;
      color: var(--color-text-accent);
    }
  }
}

#app[data-theme="cyberpunk"] .gear h2.engaged {
  text-shadow: 0 0 0.5rem var(--color-text-accent);
}
</style>
