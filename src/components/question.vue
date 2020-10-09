<template>
  <div>
    <v-card
      class="mx-auto my-12"
      width="100%"
      color="grey lighten-5"
      elevation="0"
    >
      <div>
        <v-img
          height="250"
          width="100%"
          :src="questions.questionUrl"
          contain
        ></v-img>
        <v-img
          v-if="mode == 'answer' && questions.answerUrl"
          height="250"
          width="100%"
          :src="questions.answerUrl"
          contain
        ></v-img>
        <div v-if="mode == 'answer' && questions.guide">
          <v-divider class="mx-4 my-5"></v-divider>
          <div class="justify-center d-flex">
            <v-btn width="50%" class="title"
              >{{ questions.guide.label }}
            </v-btn>
          </div>
        </div>
        <div v-if="mode == 'answer' && questions.tags">
          <v-divider class="mx-4 mt-2"></v-divider>
          <v-chip-group column>
            <v-chip dense v-for="(x, i) in questions.tags" :key="i">{{
              x.label
            }}</v-chip>
          </v-chip-group>
        </div>
        <v-overlay :z-index="zIndex" :value="overlay"
          ><v-progress-circular
            indeterminate
            color="primary"
          ></v-progress-circular>
        </v-overlay>

        <v-divider class="mx-4 mb-5"></v-divider>
        <v-row class="mx-5 justify-center">
          <v-chip-group v-model="selection" column @change="onSelectionChanged">
            <v-chip
              v-for="(g, i) in gozineha"
              :disabled="mode == 'answer'"
              :key="i"
              :class="`${g.padding} title font-weight-black ${
                mode == 'answer' && questions.answer == i
                  ? 'green lighten-2 white--text'
                  : ''
              } ${
                selection == i && (mode != 'answer' || questions.answer != i)
                  ? mode == 'answer'
                    ? 'red darken-2 white--text'
                    : 'indigo white--text'
                  : ''
              }`"
              >{{ g.label }}</v-chip
            >
          </v-chip-group>
          <v-icon class="mr-15" v-if="mode == 'answer'">{{
            difficultiIcon
          }}</v-icon>
        </v-row>
      </div>
      <v-divider class="mx-4 my-5"></v-divider>

      <v-card-actions>
        <v-btn width="48%" @click="(e) => $emit('nxt', e)"> سوال بعدی</v-btn>
        <v-btn width="48%" @click="(e) => $emit('prw', e)">
          سوال قبلی</v-btn
        ></v-card-actions
      >
      <v-divider class="mx-4 my-5"></v-divider>
      <v-dialog v-model="dialog" width="500">
        <template v-slot:activator="{ on, attrs }">
          <v-btn color="indigo accent" v-bind="attrs" v-on="on" width="100%">
            پایان آزمون</v-btn
          >
        </template>

        <v-card class="text-center">
          <v-card-title class="headline grey lighten-2 text-center">
            پایان دادن به آزمون
          </v-card-title>

          <v-card-text class="mt-10 title">
            مطمينید که آزمون را تمام میکنید؟
          </v-card-text>

          <v-divider></v-divider>

          <v-card-actions>
            <v-spacer></v-spacer>
            <v-btn color="primary" text @click="dialog = false"> خیر </v-btn>
            <v-btn
              color="primary"
              text
              @click="(overlay = !overlay), (dialog = false)"
            >
              بله
            </v-btn>
          </v-card-actions>
        </v-card>
      </v-dialog>
    </v-card>
    <v-overlay :z-index="zIndex" :value="overlay"
      ><v-progress-circular indeterminate color="primary"></v-progress-circular>
    </v-overlay>
  </div>
</template>
<script>
export default {
  props: {
    questions: {
      type: Object,
      default: () => ({
        questionUrl: "/download.jpg",
        answerUrl: "/download-2.jpg",
        tags: [{ label: "فیزیک" }, { label: "مهم" }, { label: "خیلی سخت" }],
        answer: 1,
        difficulty: 3,
        guide: { label: " تماشای ویدیوی این مبحث", url: "" },
      }),
    },

    mode: {
      type: String,
      default: "quiz",
    },
    value: {
      type: Number,
      default: -1,
    },
    gozineha: {
      type: Array,
      default: () => [
        {
          label: "الف",
          padding: "px-md-10 px-7 py-4 ",
        },
        {
          label: "ب",
          padding: "px-md-10 px-8 py-4",
        },
        {
          label: "ج",
          padding: "px-md-10 px-8 py-4 ",
        },
        {
          label: "د",
          padding: "px-md-10 px-8 py-4 ",
        },
      ],
    },
    difficultyMap: {
      type: Array,
      default: () => [
        {
          dif: 1,
          icon: "mdi-home",
        },
        {
          dif: 2,
          icon: "mdi-home",
        },
        {
          dif: 3,
          icon: "mdi-home",
        },
        {
          dif: 4,
          icon: "mdi-home",
        },
      ],
    },
  },
  data: (vm) => ({
    dialog: false,
    selection: vm.value,
    overlay: false,
    zIndex: 1,
  }),
  watch: {
    value() {
      console.log("u", this.value);
      this.selection = this.value;
    },
  },
  computed: {
    difficultiIcon() {
      const df = this.difficultyMap.filter(
        (i) => i.dif == this.questions.difficulty
      );
      return df.length > 0 ? df[0].icon : "";
    },
  },
  methods: {
    onSelectionChanged() {
      this.$emit("input", this.selection);
      console.log("change");
    },
    finishTest() {
      (this.dialog = false), this.$emit("finishtest");
    },
  },
};
</script>
