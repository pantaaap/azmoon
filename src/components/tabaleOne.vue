<template>
  <v-data-table
    :headers="headers"
    :items="desserts"
    class="elevation-1"
    hide-default-footer
    @click:row="handleClick"
  ></v-data-table>
</template>
<script>
export default {
  methods: {
    handleClick(e) {
      this.$emit("subjectnum", e.number - 1);
    },
  },
  props: {
    subjects: {
      type: Array,
      default: () => {
        [];
      },
    },
  },

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
          number: 1,
        },
        {
          name: "شیمی",
          count: 75,
          number: 2,
        },
        {
          name: "ریاضی",
          count: 75,
          number: 3,
        },
        {
          name: "زبان",
          count: 25,
          number: 4,
        },
        {
          name: "عربی",
          count: 25,
          number: 5,
        },
      ],
    };
  },
};
</script>