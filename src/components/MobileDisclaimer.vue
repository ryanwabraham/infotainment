<template>
  <section id="mobile-disclaimer">
    <h2>This demo is only available on desktop devices, sorry.</h2>
  </section>
</template>

<script>
export default {
  name: "MobileDisclaimer"
};
</script>

<style scoped lang="scss">
#mobile-disclaimer {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  display: flex;
  align-items: center;
  justify-content: center;
  text-align: center;
  background: var(--color-bg);
  z-index: 2;
  padding: 2rem;

  @media only screen and (min-width: 1000px) {
    display: none;
  }
}
</style>
