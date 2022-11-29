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
  methods: {
    changeSerie() {
      axios
        .get("https://www.breakingbadapi.com/api/characters", {
          params: {
            category: this.store.statusValue,
          },
        })
        .then((resp) => {
          this.store.characters = resp.data;
        });
    },
  },
  created() {
    this.changeSerie();
  },
};
</script>

<template>
  <main>
    <AppSearch @change="changeSerie" />
    <AppSection />
  </main>
</template>

<style lang="scss" scoped>
@import "/src/style/variables.scss";
</style>
