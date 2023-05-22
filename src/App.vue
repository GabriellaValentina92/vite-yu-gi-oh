<script>
import appHeader from "./components/appHeader.vue";
import mainBox from "./components/mainBox.vue";
import numberCard from "./components/numberCard.vue";
import axios from "../node_modules/axios";
import { store } from "../store";

export default {
  components: {
    appHeader,
    mainBox,
    numberCard,
  },

  data() {
    return {
      store,
    };
  },

  created() {
    axios
      .get("https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0")
      .then((response) => (this.store.listCard = response.data));
  },
};
</script>

<template>
  <appHeader />
  <numberCard />
  <mainBox />
</template>

<style lang="scss">
@use "../src/assets/style/general.scss";
</style>
