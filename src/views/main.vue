<template>
  <span>
    <tempNavbar class="d-md-none" />
    <v-row>
      <v-col
        cols="3"
        lg="2"
        class="d-none d-md-flex flex-column"
        style="max-height: 100%"
      >
        <timer class="mt-6 mb-8" />
        <div style="overflow: scroll; max-height: 600px">
          <pasokhnameh />
        </div>
      </v-col>
      <v-col cols="12" md="6" lg="8">
        <div class="justify-center d-flex mb-n8">
          <v-card width="100%" rounded color="grey lighten-3">
            <v-row justify="space-between mx-7 my-10 ">
              <span class="title">مرحله اول</span>
              <span class="headline">کنکور علوم تجربی ۱۴۰۰</span>
              <span class="title">۱۰ مهر ۱۳۹۹</span>
            </v-row>
          </v-card>
        </div>
        <v-content>
          <question />
        </v-content>
      </v-col>
      <v-col cols="3" lg="2" class="d-none d-md-flex flex-column">
        <automate class="my-5 ml-2 mr-2" /> <tabaleOne class="mx-2" />
      </v-col>
    </v-row>
  </span>
</template>
<script>
import question from "./../components/question";
import pasokhnameh from "./../components/pasokhnameh";
import tabaleOne from "./../components/tabaleOne";
import automate from "./../components/automate";
import timer from "./../components/timer";
import tempNavbar from "./../components/tempNavbar";
export default {
  components: {
    question,
    pasokhnameh,
    tabaleOne,
    automate,
    timer,
    tempNavbar,
  },
};
</script>