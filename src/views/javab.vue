<template>
  <div>
    <v-row width="100%">
      <tableTwo />
    </v-row>
    <v-row>
      <v-col cols="12" md="6"> <rank /></v-col>
      <v-col cols="12" md="6"> <rankComp /></v-col>
    </v-row>
    <v-data-table
      :headers="headers"
      :items="desserts"
      class="elevation-1"
      hide-default-footer
    ></v-data-table>
    <pasokhnameh />
  </div>
</template>
<script>
import pasokhnameh from "./../components/pasokhnameh";
import tableTwo from "./../components/tableTwo";
import rank from "./../components/rank";
import rankComp from "./../components/rankComp";
export default {
  components: {
    pasokhnameh,
    tableTwo,
    rank,
    rankComp,
  },
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
          arr.push({ number: i + 1, numberF: (i + 1).toLocaleString("fa") });
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
      onGozineChaged(q, g) {
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