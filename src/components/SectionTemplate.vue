<template>
   <section class="section">
      <slot></slot>
   </section>
</template>

<style lang="scss" scoped>
@import "../styles/abstracts.scss";

.section {
   background-color: $color-background-2;
   border-radius: 0.5rem;
   padding: 0.75rem;
   position: relative;
   overflow: hidden;
   @include responsive($screen-tablet-s) {
      padding: 1.5rem;
   }
}
</style>