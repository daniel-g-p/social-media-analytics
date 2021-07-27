<template>
   <div class="button">
      <input
         class="button__input"
         type="radio"
         name="network"
         v-bind:id="name"
      />
      <div class="button__outline" v-bind:style="backgroundStyle"></div>
      <label class="button__label" v-bind:for="name">
         <div class="button__icon">
            <img v-bind:src="imageSource" class="button__icon" />
         </div>
         <span class="button__text">{{ capitalizedName }}</span>
      </label>
   </div>
</template>

<script>
export default {
   props: ["name", "background", "backgroundType"],
   computed: {
      capitalizedName() {
         return this.name[0].toUpperCase() + this.name.slice(1);
      },
      imageSource() {
         return `../img/icon-${this.name}.svg`;
      },
      backgroundStyle() {
         if (this.backgroundType === "solid") {
            return { backgroundColor: this.background };
         } else {
            return { backgroundImage: this.background };
         }
      },
   },
};
</script>

<style lang="scss" scoped>
@import "../styles/abstracts.scss";

.button {
   position: relative;
   &__input {
      display: none;
      &:checked + .button__outline {
         width: calc(100% + 0.6em);
         height: calc(100% + 0.6em);
         top: -0.3em;
         left: -0.3em;
         opacity: 1;
      }
   }
   &__label {
      background-color: $color-background-1;
      border-radius: 0.2em;
      padding: 0.5em 0.75em;
      display: flex;
      color: $color-body-1;
      position: relative;
      z-index: 2;
      cursor: pointer;
      transition: padding-left 0.25s ease;
      &:hover {
         padding-left: 1.25em;
      }
   }
   &__outline {
      display: block;
      position: absolute;
      top: 0;
      left: 0;
      z-index: 0;
      width: 100%;
      height: 100%;
      border-radius: 0.3em;
      opacity: 0;
      transition-property: left, top, width, height, opacity;
      transition-duration: 0.25s;
      transition-timing-function: ease;
      &::after {
         content: "";
         position: absolute;
         z-index: 1;
         top: 0.15em;
         left: 0.15em;
         width: calc(100% - 0.3em);
         height: calc(100% - 0.3em);
         background-color: $color-background-2;
         border-radius: 0.25em;
      }
   }
   &__icon {
      width: 1em;
      height: 1em;
      display: flex;
      justify-content: center;
      align-items: center;
      margin-right: 0.25em;
      img {
         max-width: 100%;
         max-height: 100%;
      }
   }
}
</style>