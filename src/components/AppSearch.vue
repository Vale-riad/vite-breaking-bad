<script>
import { store } from "../store";
export default {
  name: "AppSearch",
  data() {
    return {
      store,
    };
  },
};
</script>
<template>
  <div class="container">
    <div class="col-auto mt-3 mb-3">
      <label for="series">Choose a series:</label>
      <select
        class="form-select w-auto"
        v-model="store.statusValue"
        @change="$emit('filter')"
      >
        <option value="" selected>Select category</option>
        <option value="Breaking Bad">Breaking Bad</option>
        <option value="Better Call Saul">Better Call Saul</option>
        <option value="Breaking Bad, Better Call Saul">
          Breaking Bad and Better Call Saul
        </option>
      </select>
    </div>
  </div>
</template>
<style lang="scss" scoped></style>
