<template>
   <div class="options">
      <option-button
         v-for="network in networks"
         v-bind:key="network.name"
         v-bind="network"
         v-on:select-network="selectNetwork"
      ></option-button>
   </div>
</template>

<script>
import OptionButton from "./OptionButton.vue";

export default {
   components: {
      "option-button": OptionButton,
   },
   data() {
      return {
         networks: [
            {
               name: "facebook",
               requestAddress: "https://www.facebook.com",
               background: "#1778f2",
               backgroundType: "solid",
            },
            {
               name: "instagram",
               requestAddress: "https://www.instagram.com",
               background:
                  "linear-gradient(to bottom right, #f58529, #feda77, #dd2a7b, #515bd4, #8134af)",
               backgroundType: "gradient",
            },
            {
               name: "twitter",
               requestAddress: "https://www.twitter.com",
               background: "#00acee",
               backgroundType: "solid",
            },
            {
               name: "youtube",
               requestAddress: "https://www.youtube.com",
               background: "#ff0000",
               backgroundType: "solid",
            },
            {
               name: "tiktok",
               requestAddress: "https://www.tiktok.com",
               background: "linear-gradient(to bottom right, #00f2ea, #ff004f)",
               backgroundType: "gradient",
            },
            {
               name: "pinterest",
               requestAddress: "https://www.pinterest.com",
               background: "#e60023",
               backgroundType: "solid",
            },
         ],
      };
   },
   methods: {
      selectNetwork(network) {
         const input = this.networks.find((n) => n.name === network);
         this.$emit("select-network", input);
      },
   },
};
</script>

<style lang="scss" scoped>
@import "../styles/abstracts.scss";

.options {
   display: grid;
   gap: 0.75rem;
   @include responsive($screen-mobile-m) {
      grid-template-columns: 1fr 1fr;
   }
}
</style>