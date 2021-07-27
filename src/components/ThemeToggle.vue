<template>
   <div class="toggle">
      <span class="toggle__label">{{ theme }} theme</span>
      <div
         class="toggle__button"
         v-bind:class="buttonClass"
         v-on:click="changeTheme"
      >
         <div class="toggle__circle"></div>
      </div>
   </div>
</template>

<script>
export default {
   data() {
      return {
         isDark: true,
      };
   },
   computed: {
      theme() {
         return this.isDark ? "dark" : "light";
      },
      buttonClass() {
         return `toggle__button--${this.theme}`;
      },
   },
   methods: {
      changeTheme() {
         this.isDark = !this.isDark;
         this.$emit("change-theme", this.theme);
      },
   },
};
</script>

<style lang="scss" scoped>
@import "../styles/abstracts.scss";
.toggle {
   justify-self: flex-end;
   display: flex;
   justify-content: flex-end;
   align-items: center;
   &:hover {
      opacity: 1;
   }
   &__label {
      font-size: 0.8rem;
      color: $color-body-1;
      text-transform: uppercase;
      font-weight: 700;
      margin-right: 0.5rem;
      opacity: 0.5;
   }
   &__button {
      display: block;
      width: 1.75rem;
      height: 1rem;
      border-radius: 0.75rem;
      background-color: $color-body-1;
      position: relative;
      cursor: pointer;
      opacity: 0.5;
      transition: opacity 0.25s ease;
      &:hover {
         opacity: 1;
      }
      &--dark > div {
         left: 0.15rem;
      }
      &--light > div {
         left: 0.875rem;
      }
   }
   &__circle {
      display: block;
      width: 0.7rem;
      height: 0.7rem;
      background-color: $color-background-1;
      border-radius: 50%;
      position: absolute;
      top: 0.15rem;
      transition: left 0.25s ease;
   }
}
</style>