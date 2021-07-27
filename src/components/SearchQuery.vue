<template>
   <form class="search-form">
      <input
         type="text"
         name="username"
         placeholder="username"
         class="search-form__input"
         maxlength="50"
         v-model="username"
      />
      <button class="search-form__button">
         Find {{ username }} {{ networkText }}
      </button>
   </form>
</template>

<script>
export default {
   props: ["network"],
   data() {
      return {
         username: "",
      };
   },
   computed: {
      networkText() {
         return this.network ? `on ${this.network}` : "";
      },
   },
};
</script>

<style lang="scss" scoped>
@import "../styles/abstracts.scss";

.search-form {
   flex-grow: 1;
   display: flex;
   flex-direction: column;
   align-items: stretch;
   text-align: center;
   &__input {
      flex-grow: 1;
      font-size: 1.25rem;
      text-transform: uppercase;
      color: $color-body-1;
      background-color: $color-background-1;
      border: 0.15em solid $color-background-1;
      outline: none;
      display: flex;
      justify-content: center;
      align-items: center;
      padding: 1.35rem 1.5rem;
      letter-spacing: 0.1em;
      text-align: center;
      font-weight: 700;
      border-radius: 0.2em;
      transition: border-color 0.25s ease;
      &::placeholder {
         color: $color-body-2;
      }
      &:focus {
         border-color: $color-body-1;
      }
   }
   &__button {
      overflow: hidden;
      color: $color-background-1;
      background-color: $color-body-1;
      margin-top: 0.75rem;
      border: none;
      outline: none;
      font-size: 0.8rem;
      padding: 0.6em 1em;
      line-height: 1.25;
      border-radius: 0.2em;
      text-transform: uppercase;
      letter-spacing: 0.1em;
      font-weight: 700;
      cursor: pointer;
      transition: color 0.25s ease, background-color 0.25s ease;
      &:hover {
         background-color: $color-background-1;
         color: $color-body-1;
      }
   }
}
</style>