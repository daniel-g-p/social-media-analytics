<template>
   <div class="search-block">
      <network-options v-on:select-network="selectNetwork"></network-options>
      <div class="separator"></div>
      <search-query v-bind:network="network"></search-query>
   </div>
</template>

<script>
import NetworkOptions from "./NetworkOptions.vue";
import SearchQuery from "./SearchQuery.vue";

export default {
   components: {
      "network-options": NetworkOptions,
      "search-query": SearchQuery,
   },
   data() {
      return {
         network: "",
      };
   },
   methods: {
      selectNetwork(network) {
         this.network = network;
      },
   },
};
</script>

<style lang="scss" scoped>
@import "../styles/abstracts.scss";

.search-block {
   width: 100%;
   display: flex;
   flex-direction: column;
   align-items: stretch;
   @include responsive($screen-tablet-l) {
      flex-direction: row;
      justify-content: space-between;
   }
}

.separator {
   display: block;
   width: 100%;
   height: 0.25rem;
   border-radius: 0.125rem;
   background-color: $color-background-1;
   margin: 0.75rem 0;
   @include responsive($screen-tablet-l) {
      width: 0.25rem;
      height: auto;
      align-self: stretch;
      margin: 0 0.75rem;
   }
}
</style>