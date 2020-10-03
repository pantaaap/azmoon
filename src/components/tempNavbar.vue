<template>
  <v-card>
    <v-app-bar>
      <v-app-bar-nav-icon @click.stop="drawer = !drawer"> </v-app-bar-nav-icon>
    </v-app-bar>

    <v-navigation-drawer v-model="drawer" temporary app fixed absolute right>
      <pasokhnameh
    /></v-navigation-drawer>
  </v-card>
</template>

<script>
import pasokhnameh from "./../components/pasokhnameh";
export default {
  components: {
    pasokhnameh,
  },
  data: () => ({
    drawer: false,
    group: null,
  }),

  watch: {
    group() {
      this.drawer = false;
    },
  },
};
</script>