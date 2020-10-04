<template>
  <div>
    <v-banner justify="center">پاسخنامه</v-banner>
    <v-sheet
      tile
      justify-center="center"
      width="100%"
      outlined
      class="questions_index"
    >
      <div
        v-for="question in questions"
        :key="question.number"
        class="py-0 d-flex flex-column"
        :style="question.ord"
      >
        <div class="py-0 d-flex flex-row ps-15 pe-5">
          <v-chip-group
            v-model="selection"
            active-class="deep-purple accent-4 white--text"
            column
            class="py-0"
          >
            <v-chip small class="px-1 py-0"> الف</v-chip>

            <v-chip small class="px-2 py-0">ب</v-chip>

            <v-chip small class="px-2 py-0">ج</v-chip>

            <v-chip small class="px-2 py-0">د</v-chip>
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
    questions: {
      type: Array,
      default: () => {
        let arr = [];

        for (let i = 0; i < 200; i++) {
          arr.push({
            number: i + 1,
            numberF: (i + 1).toLocaleString("fa"),
            ord: "order:" + (200 - i),
          });
        }
        return arr;
      },
      value: {
        type: Array,
        default: () => [],
      },
    },
    data() {
      const chbxVals = {};
      this.questions.forEach((q) => {
        chbxVals[q.number] = {};
        q.gozineha.forEach((g) => {
          chbxVals[q.number][g.number] = false;
        });
      });
      return {
        inputValue: this.value,
        checkboxVals: chbxVals,
      };
    },
    methods: {
      onGozineChanged(q, g) {
        if (
          this.inputValue[q.number] &&
          this.inputValue[q.number] === g.number
        ) {
          this.inputValue[q.number] = -1;
        } else {
          this.inputValue[q.number] = g.number;
        }
        for (const n in this.checkboxVals[q.number]) {
          this.checkboxVals[q.number][n] = false;
        }
        if (!this.checkboxVals[q.number]) {
          this.checkboxVals[q.number] = {};
        }
        this.checkboxVals[q.number][g.number] = true;
        console.log(this.inputValue);
      },
      isAnsweredForQuestion(q, g) {
        return (
          this.inputValue[q.number] === g.number ||
          (this.mode === "a" && q.answer === g.number)
        );
      },
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