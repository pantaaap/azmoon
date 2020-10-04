<template>
  <v-data-table
    :headers="headers"
    :items="desserts"
    class="elevation-1"
    hide-default-footer
  ></v-data-table>
</template>
<script>
export default {
  data() {
    return {
      headers: [
        {
          text: "نام درس",
          align: "start",
          sortable: false,
          value: "name",
        },
        { text: "درست", value: "C" },
        { text: " غلط", value: "W" },
        { text: " نزده", value: "E" },
        { text: "رتبه  ", value: "T" },
        { text: "تراز", value: "R" },
        { text: "تراز مطابق با آزمون سراسری ۹۸", value: "hashtT" },
        { text: "رتبه مطابق با آزمون سراسری ۹۸", value: "hashtR" },
        { text: "تراز مطابق با آزمون سراسری ۹۹", value: "nohT" },
        { text: "رتبه مطابق با آزمون سراسری ۹۹", value: "nohR" },
      ],
      desserts: [
        {
          name: " فیزیک",
          C: 10,
          W: 10,
          E: 3,
          T: 12349000,
          R: 78,
          hashtT: 12349000,
          hashtR: 78,
          nohT: 12345000,
          nohR: 100,
        },
        {
          name: " شیمی",
          C: 10,
          W: 10,
          E: 3,
          T: 12349000,
          R: 78,
          hashtT: 12349000,
          hashtR: 78,
          nohT: 12345000,
          nohR: 100,
        },
        {
          name: " فیزیک",
          C: 10,
          W: 10,
          E: 3,
          T: 12349000,
          R: 78,
          hashtT: 12349000,
          hashtR: 78,
          nohT: 12345000,
          nohR: 100,
        },
        {
          name: "ریاضی",
          C: 10,
          W: 10,
          E: 3,
          T: 12349000,
          R: 78,
          hashtT: 12349000,
          hashtR: 78,
          nohT: 12345000,
          nohR: 100,
        },
        {
          name: "ادبیات",
          C: 10,
          W: 10,
          E: 3,
          T: 12349000,
          R: 78,
          hashtT: 12349000,
          hashtR: 78,
          nohT: 12345000,
          nohR: 100,
        },
        {
          name: " عربی",
          C: 10,
          W: 10,
          E: 3,
          T: 12349000,
          R: 78,
          hashtT: 12349000,
          hashtR: 78,
          nohT: 12345000,
          nohR: 100,
        },
        {
          name: " دینی",
          C: 10,
          W: 10,
          E: 3,
          T: 12349000,
          R: 78,
          hashtT: 12349000,
          hashtR: 78,
          nohT: 12345000,
          nohR: 100,
        },
        {
          name: " زبان",
          C: 10,
          W: 10,
          E: 3,
          T: 12349000,
          R: 78,
          hashtT: 12349000,
          hashtR: 78,
          nohT: 12345000,
          nohR: 100,
        },
      ],
    };
  },
};
</script>