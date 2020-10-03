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
        { text: "تعداد سوال", value: "count" },
        { text: "شماره سوال", value: "number" },
      ],
      desserts: [
        {
          name: " فیزیک",
          count: 75,
          number: "1 -75 ",
        },
        {
          name: "شیمی",
          count: 75,
          number: "76 -150 ",
        },
        {
          name: "ریاضی",
          count: 75,
          number: "151 -225",
        },
        {
          name: "زبان",
          count: 25,
          number: "76 -100",
        },
        {
          name: "عربی",
          count: 25,
          number: "26 -50",
        },
      ],
    };
  },
};
</script>