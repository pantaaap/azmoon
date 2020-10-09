<template>
  <div v-resize="onResize">
    <v-banner justify="center">پاسخنامه</v-banner>
    <v-sheet tile width="100%" outlined :style="pasokhStyle" ref="SheetWidth">
      <div
        v-for="question in questionsList"
        :key="question.number"
        :class="`py-0 d-flex flex-column ${
          selectedQ == question.number ? 'grey lighten-4' : ''
        }`"
        :style="question.ord"
      >
        <div class="py-0 d-flex flex-row ps-15 pe-5" style="direction: rtl">
          <v-chip-group column>
            <v-chip
              v-for="(g, i) in gozineha"
              :disabled="mode == 'answer'"
              :key="i"
              :class="`${g.padding} py-0 ${
                mode == 'answer' && questions.answer == i
                  ? 'green lighten-2 white--text'
                  : ''
              } ${
                question.selected == i &&
                (mode != 'answer' || questions.answer != i)
                  ? mode == 'answer'
                    ? 'red darken-2 white--text'
                    : 'indigo white--text'
                  : ''
              }`"
              >{{ g.label }}</v-chip
            >
          </v-chip-group>
          <v-spacer></v-spacer>
          <span class="my-auto">{{ question.numberF }}</span>
        </div>
        <v-divider></v-divider>
      </div>
    </v-sheet>
  </div>
</template>
<script>
export default {
  props: {
    mode: {
      type: String,
      default: "a",
    },
    selectedQ: {
      type: Number,
      deafault: 1,
    },
    gozineha: {
      type: Array,
      default: () => [
        {
          label: "الف",
          padding: "px-1  ",
        },
        {
          label: "ب",
          padding: "px-2  ",
        },
        {
          label: "ج",
          padding: "px-2 ",
        },
        {
          label: "د",
          padding: "px-2 ",
        },
      ],
    },
    answerSheet: {
      type: Object,
      default: () => ({}),
    },
    questions: {
      type: Array,
      default: () => {
        let arr = [];

        for (let i = 0; i < 6; i++) {
          arr.push({
            number: i + 1,
            numberF: (i + 1).toLocaleString("fa"),
            ord: "order:" + (200 - i),
          });
        }
        return arr;
      },
    },
    value: {
      type: Array,
      default: () => [],
    },
    column: {
      type: Number,
      default: 1,
    },
  },
  data() {
    return {
      inputValue: this.value,
      selection: null,
    };
  },
  computed: {
    questionsList() {
      return this.questions.map((q, i) => ({
        ...q,
        numberF: (i + 1).toLocaleString("fa"),
        number: i,
        selected: this.answerSheet[i],
      }));
    },
    pasokhStyle() {
      return { columnCount: this.column, direction: "ltr" };
    },
  },
  methods: {
    onResize() {
      if (this.$refs.SheetWidth.$el.offsetWidth >= 1220) {
        this.column = 5;
      } else if (this.$refs.SheetWidth.$el.offsetWidth >= 920) {
        this.column = 3;
      } else if (this.$refs.SheetWidth.$el.offsetWidth >= 500) {
        this.column = 2;
      } else {
        this.column = 1;
      }
    },
  },
  mounted() {
    this.onResize();
  },
  watch: {
    selectedQ() {
      this.$refs.SheetWidth.$el.children[0].scrollTop = this.selectedQ * 10;
    },
  },
};
</script>

<style scoped>
.questions_index {
  column-count: 5;
  justify-items: end;
  /* height: 800px;
  display: flex;
  flex-direction: column;
  flex-wrap: wrap;

  overflow-x: auto;*/
}
</style>
