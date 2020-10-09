<template>
  <v-card>
    <v-app-bar>
      <v-app-bar-nav-icon @click.stop="drawer = !drawer"> </v-app-bar-nav-icon>
    </v-app-bar>

    <v-navigation-drawer v-model="drawer" temporary app fixed absolute right>
      <pasokhnameh :questions="questions"
    /></v-navigation-drawer>
  </v-card>
</template>

<script>
import pasokhnameh from "./../components/pasokhnameh";
export default {
  props: {
    questions: {
      type: Array,
    },
  },
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
