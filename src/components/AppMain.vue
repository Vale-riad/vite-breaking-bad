<script>
import axios from "axios";
import { store } from "../store";

import AppSearch from "./AppSearch.vue";
import AppSection from "./AppSection.vue";

export default {
  name: "AppMain",
  components: {
    AppSearch,
    AppSection,
  },
  data() {
    return {
      store,
    };
  },
  created() {
    axios.get("https://www.breakingbadapi.com/api/characters").then((resp) => {
      this.store.characters = resp.data;
    });
  },
};
</script>

<template>
  <main>
    <AppSearch />
    <AppSection />
  </main>
</template>

<style lang="scss" scoped>
@import "/src/style/variables.scss";
</style>
