<script>
import { store } from "../store";
import AppCard from "./AppCard.vue";
export default {
  name: "AppSection",
  components: {
    AppCard,
  },
  data() {
    return {
      store,
    };
  },
};
</script>
<template>
  <div class="container-lg py-5 px-5">
    <div class="container-sm">
      <h6 class="py-3">Found 62 characters</h6>
    </div>
    <div class="container-sm d-flex text-center">
      <AppCard
        v-for="character in store.characters"
        class="col-lg-2 m-2"
        :info="character"
      />
    </div>
  </div>
</template>
<style lang="scss" scoped>
.container-lg {
  background-color: var(--secondary-color);
}

.container-sm {
  flex-wrap: wrap;
  h6 {
    color: white;
    background-color: #212529;
  }
}
</style>
