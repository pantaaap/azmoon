<template>
  <div class="about">
    <v-row>
      <product />
      <product />
      <product />
      <product />
    </v-row>
  </div>
</template>
<script>
import product from "./../components/product";
export default {
  components: {
    product,
  },
};
</script>
