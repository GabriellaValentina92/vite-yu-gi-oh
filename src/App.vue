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

  methods: {
    requestDataFromApi() {
      axios
        .get("https://db.ygoprodeck.com/api/v7/cardinfo.php", {
          params: {
            num: 20,
            offset: 0,
            archetype: this.store.archetypeText,
          },
        })
        .then((response) => (this.store.cardList = response.data.data));
    },
  },

  created() {
    axios
      .get("https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0")
      .then((response) => (this.store.listCard = response.data.data));

    axios
      .get("https://db.ygoprodeck.com/api/v7/archetypes.php")
      .then((response) => (this.store.archetypesList = response.data));
  },
};
</script>

<template>
  <div class="container">
    <appHeader />
    <selectSection @performSearch="requestDataFromApi" />
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
