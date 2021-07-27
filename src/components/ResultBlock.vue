<template>
   <div class="result">
      <div class="result__border"></div>
      <h2 class="result__heading">
         Facebook data for <a href="/" class="result__username">daniel.gp</a>
      </h2>
      <div class="result__data">
         <result-field></result-field>
         <result-field></result-field>
         <result-field></result-field>
         <result-field></result-field>
      </div>
   </div>
</template>

<script>
import ResultField from "./ResultField.vue";

export default {
   components: {
      "result-field": ResultField,
   },
};
</script>

<style lang="scss" scoped>
@import "../styles/abstracts.scss";

.result {
   display: flex;
   flex-direction: column;
   justify-content: space-evenly;
   color: $color-body-1;
   padding: 0.75rem;
   &__heading {
      font-size: 1.25rem;
      font-weight: 400;
      line-height: 1.25;
      @include responsive($screen-tablet-s) {
         font-size: 1.5rem;
      }
   }
   &__username {
      color: $color-body-1;
      font-weight: 700;
      text-decoration: none;
      transition: color 0.25s ease;
      &:hover {
         color: $color-body-2;
      }
   }
   &__data {
      display: flex;
      flex-direction: column;
      align-items: center;
      padding-top: 1.5rem;
      @include responsive($screen-mobile-l) {
         display: grid;
         grid-template-columns: 1fr 1fr;
         gap: 1.5rem;
      }
      @include responsive($screen-tablet-l) {
         display: flex;
         flex-direction: row;
         justify-content: space-evenly;
         gap: 0;
      }
   }
}
</style>