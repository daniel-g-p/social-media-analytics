<template>
   <div class="data">
      <div class="data__number">54K</div>
      <div class="data__label">Followers</div>
      <div class="data__trend">
         <svg class="data__icon" viewBox="0 0 18 10">
            <path
               d="M16.5858 10H1.41421C0.523309 10 0.0771408 8.92286 0.707106 8.29289L8.29289 0.707107C8.68342 0.316583 9.31658 0.316582 9.70711 0.707106L17.2929 8.29289C17.9229 8.92286 17.4767 10 16.5858 10Z"
            />
         </svg>
         <span class="data__percentage">+2.7%</span>
      </div>
   </div>
</template>

<style lang="scss" scoped>
@import "../styles/abstracts.scss";

.data {
   display: flex;
   flex-direction: column;
   align-items: center;
   letter-spacing: 0.2em;
   margin: 1.25rem;
   &__number {
      font-size: 1.5rem;
      font-weight: 700;
      margin-bottom: 0.5rem;
      @include responsive($screen-tablet-s) {
         font-size: 2.25rem;
      }
   }
   &__label {
      text-transform: uppercase;
      font-size: 0.8rem;
      letter-spacing: 0.2em;
      margin-bottom: 1rem;
   }
   &__trend {
      color: $color-green;
      display: flex;
      align-items: center;
   }
   &__icon {
      height: 0.6rem;
      fill: currentColor;
      margin-right: 0.25rem;
   }
   &__percentage {
      letter-spacing: 0.1em;
      font-weight: 700;
      font-size: 0.8rem;
   }
}
</style>