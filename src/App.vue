<template>
   <header-block v-on:change-theme="changeTheme"></header-block>
</template>

<script>
import HeaderBlock from "./components/HeaderBlock.vue";
export default {
   data() {
      return {
         themeVariables: document.documentElement.style,
      };
   },
   components: {
      "header-block": HeaderBlock,
   },
   methods: {
      changeTheme(theme) {
         if (theme === "dark") {
            this.themeVariables.setProperty("--color-background-1", "#0d0d0d");
            this.themeVariables.setProperty("--color-background-2", "#1a1a1a");
            this.themeVariables.setProperty("--color-body-1", "#f2f2f2");
            this.themeVariables.setProperty("--color-body-2", "#262626");
         } else {
            this.themeVariables.setProperty("--color-background-1", "#ffffff");
            this.themeVariables.setProperty("--color-background-2", "#f2f2f2");
            this.themeVariables.setProperty("--color-body-1", "#0d0d0d");
            this.themeVariables.setProperty("--color-body-2", "#e5e5e5");
         }
      },
   },
};
</script>

<style lang="scss">
@import "./styles/abstracts.scss";
@font-face {
   font-family: "Bai Jamjuree";
   src: url("./fonts/bai-jamjuree-bold.woff2") format("woff2"),
      url("./fonts/bai-jamjuree-bold.woff") format("woff");
   font-weight: 700;
   font-style: normal;
}

@font-face {
   font-family: "Bai Jamjuree";
   src: url("./fonts/bai-jamjuree-regular.woff2") format("woff2"),
      url("./fonts/bai-jamjuree-regular.woff") format("woff");
   font-weight: 400;
   font-style: normal;
}

:root {
   --color-background-1: #0d0d0d;
   --color-background-2: #1a1a1a;
   --color-body-1: #f2f2f2;
   --color-body-2: #262626;
}

*,
*::before,
*::after {
   margin: 0;
   padding: 0;
   box-sizing: inherit;
   transition: background-color 0.5s ease, color 0.5s ease;
}

button,
input {
   font: 400 125%/1 "Bai Jamjuree", sans-serif;
   outline: none;
}

html {
   font: 400 125%/1 "Bai Jamjuree", sans-serif;
}

body {
   box-sizing: inherit;
}

#app {
   min-height: 100vh;
   background-color: $color-background-1;
   padding: 3rem 1.5rem;
   @include responsive($screen-tablet-s) {
      padding: 4.5rem 3rem;
   }
   @include responsive($screen-desktop-s) {
      padding: 6rem 6rem;
   }
}
</style>