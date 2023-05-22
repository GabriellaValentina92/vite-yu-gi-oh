<script>
import appHeader from "./components/appHeader.vue";
import listCard from "./components/listCard.vue";
import numberCard from "./components/numberCard.vue";
import selectSection from "./components/selectSection.vue";
import axios from "axios";
import { store } from "./store";

export default {
  components: {
    appHeader,
    listCard,
    numberCard,
    selectSection,
  },

  data() {
    return {
      store,
    };
  },

  created() {
    axios
      .get("https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0")
      .then((response) => (this.store.listCard = response.data.data));
  },
};
</script>

<template>
  <div class="container">
    <appHeader />
    <selectSection />
    <numberCard />
    <listCard />
  </div>
</template>

<style lang="scss">
@use "../src/assets/style/general.scss";

.container {
  background-color: rgb(245, 154, 8);
}
</style>
