<script>
import appHeader from "./components/appHeader.vue";
import mainBox from "./components/mainBox.vue";
import numberCard from "./components/numberCard.vue";
import selectSection from "./components/selectSection.vue";
import axios from "axios";
import { store } from "./store";

export default {
  components: {
    appHeader,
    mainBox,
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
      .then((response) => (this.store.listCard = response.data));
  },
};
</script>

<template>
  <appHeader />
  <div class="container">
    <selectSection />
    <numberCard />
    <mainBox />
  </div>
</template>

<style lang="scss">
@use "../src/assets/style/general.scss";

.container {
  background-color: rgb(245, 154, 8);
}
</style>
