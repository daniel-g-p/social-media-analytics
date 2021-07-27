<template>
   <header class="header">
      <h1 class="header__heading">Social Media Dashboard</h1>
      <theme-toggle v-on:change-theme="changeTheme"></theme-toggle>
   </header>
</template>

<script>
import ThemeToggle from "./ThemeToggle.vue";

export default {
   components: {
      "theme-toggle": ThemeToggle,
   },
   methods: {
      changeTheme(theme) {
         this.$emit("change-theme", theme);
      },
   },
};
</script>

<style lang="scss" scoped>
@import "../styles/abstracts.scss";
.header {
   display: grid;
   gap: 1.5rem;
   @include responsive($screen-desktop-s) {
      grid-template-columns: 1fr max-content;
   }
   &__heading {
      color: $color-body-1;
      text-transform: uppercase;
      font-size: 1.5rem;
      letter-spacing: 0.1em;
      line-height: 1.25;
      @include responsive($screen-tablet-s) {
         font-size: 2.25rem;
      }
   }
}
</style>