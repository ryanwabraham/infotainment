<template>
  <section id="theme-picker">
    <div>
      <h2>Select a Theme</h2>
      <ul>
        <li>
          <button v-on:click="changeTheme('light')">
            <ul class="swatch-wrapper">
              <li style="background-color: #ececec"></li>
              <li style="background-color: #ffffff"></li>
              <li style="background-color: #aaaaaa"></li>
              <li style="background-color: #000000"></li>
              <li style="background-color: #7ea0fa"></li>
            </ul>
            <h3>Light</h3>
          </button>
        </li>
        <li>
          <button v-on:click="changeTheme('dark')">
            <ul class="swatch-wrapper">
              <li style="background-color: #1d2035"></li>
              <li style="background-color: #2c3e5f"></li>
              <li style="background-color: #8cb6f6"></li>
              <li style="background-color: #a3dbff"></li>
              <li style="background-color: #e6358c"></li>
            </ul>
            <h3>Dark</h3>
          </button>
        </li>
        <li>
          <button v-on:click="changeTheme('cyberpunk')">
            <ul class="swatch-wrapper">
              <li style="background-color: #1d2035"></li>
              <li style="background-color: #1d2035"></li>
              <li style="background-color: #62aca3"></li>
              <li style="background-color: #71f3fd"></li>
              <li
                style="background: linear-gradient(180deg, #e5092f 0%, #e30f7e 100%)"
              ></li>
            </ul>
            <h3>Cyberpunk</h3>
          </button>
        </li>
      </ul>
    </div>
  </section>
</template>

<script>
export default {
  name: "ThemePicker",
  methods: {
    changeTheme: theme => {
      const themePicker = document.getElementById("theme-picker");
      const app = document.getElementById("app");
      const paletteButton = document.querySelector(".card.button.active");
      app.setAttribute("data-theme", theme);
      themePicker.classList.remove("open");
      if (paletteButton) paletteButton.classList.remove("active");
    }
  }
};
</script>

<style scoped lang="scss">
#theme-picker {
  width: 100%;
  height: 100%;
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  display: flex;
  align-items: center;
  justify-content: center;
  background: var(--color-bg);
  opacity: 0;
  transition-duration: 0.25s;

  &.open {
    opacity: 1;
    transition-duration: 0.25s;
    z-index: 1;
  }

  div {
    text-align: center;
  }
}

h2 {
  color: var(--color-text-accent);
}

ul {
  height: 150px;
  margin: 0px;
  padding: 0px;
  display: flex;
  align-items: center;
  justify-content: center;
  list-style-type: none;
}

li {
  margin: 0px 10px;
}

button {
  -webkit-appearance: none;
  background-color: var(--color-bg-light);
  color: inherit;
  padding: 0px 20px;
  font-size: inherit;
  border-radius: 10px;
  border: none;
  cursor: pointer;
}

.swatch-wrapper {
  height: auto;
  margin: 1.5rem 0px 0px 10px;

  li {
    width: 30px;
    height: 30px;
    border: 2px solid #fff;
    border-radius: 50%;
    margin: 0px 0px 0px -10px;
  }
}

#app[data-theme="cyberpunk"] {
  button {
    border: var(--border);
  }
}
</style>
