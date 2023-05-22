<script>
import appHeader from "./components/appHeader.vue";
import mainBox from "./components/mainBox.vue";

export default {
  components: {
    appHeader,
    mainBox,
  },
};
</script>

<template>
  <appHeader />
  <maniBox />
</template>

<style lang="scss">
@use "../src/assets/style/general.scss";
</style>
