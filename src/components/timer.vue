<template>
  <v-card
    class="mx-auto justify-center align-center d-flex-column"
    width="100%"
    outlined
    color="grey lighten-3"
    elevation="1"
  >
    <div class="display-2 mt-5 text-center" v-show="!show">{{ remaining }}</div>
    <v-row>
      <v-col cols="3">
        <v-checkbox class="mr-5" small v-model="show"></v-checkbox>
      </v-col>
      <v-col
        ><span class="body-2 d-inline-block mt-5 mr-n3"> عدم نمایش زمان</span>
      </v-col></v-row
    >
  </v-card>
</template>

<script>
import moment from "moment-jalaali";
export default {
  props: {
    totalTime: {
      type: Number,
      default: () => 90,
    },
  },
  data: (vm) => {
    return {
      start_at: moment().add(vm.totalTime, "minute"),
      remaining: "",
      show: false,
    };
  },
  methods: {
    updateTime() {
      setTimeout(() => {
        this.updateTimeString();
        this.updateTime();
      }, 100);
    },
    updateTimeString() {
      const dur = moment.duration(
        this.start_at.diff(moment(), "seconds") * 1000
      );
      this.remaining =
        dur.hours() +
        ":" +
        (dur.minutes() >= 10 ? "" : "0") +
        dur.minutes() +
        ":" +
        (dur.seconds() >= 10 ? "" : "0") +
        dur.seconds();
    },
  },
  mounted() {
    this.updateTime();
  },
};
</script>
