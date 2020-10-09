<template>
  <span>
    <tempNavbar class="d-md-none" :questions="questions" />
    <v-row>
      <v-col
        cols="3"
        lg="2"
        class="d-none d-md-flex flex-column"
        style="max-height: 100%"
      >
        <timer class="mb-8" />
        <div style="overflow: scroll; max-height: 600px" ref="scrollHelp">
          <pasokhnameh
            :answer-sheet="answerSheet"
            :questions="questions"
            :selectedQ="currentIndex"
          />
        </div>
      </v-col>
      <v-col cols="12" md="6" lg="8">
        <div class="justify-center d-flex mb-n8">
          <v-card width="100%" rounded color="grey lighten-3">
            <v-row justify="space-between" class="mx-7 my-10">
              <span class="title">مرحله اول</span>
              <span class="headline">کنکور علوم تجربی ۱۴۰۰</span>
              <span class="title">۱۰ مهر ۱۳۹۹</span>
            </v-row>
          </v-card>
        </div>
        <v-content>
          <question
            v-model="currentAnswer"
            :questions="currentQuestion"
            @input="onAnswerChanged"
            @nxt="next"
            @prw="prw"
          />
        </v-content>
      </v-col>
      <v-col cols="3" lg="2" class="d-none d-md-flex flex-column">
        <automate class="mb-5 ml-2 mr-2" @automate="autoNext = !autoNext" />
        <tabaleOne class="mx-2" @subjectnum="subNumHandler" />
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

  props: {
    questions: {
      type: Array,
      default: () => [
        {
          questionUrl: "/download.jpg",
          answerUrl: "/download-2.jpg",
          tags: [{ label: "فیزیک" }, { label: "مهم" }, { label: "خیلی سخت" }],
          answer: 1,
          difficulty: 3,
          guide: { label: " تماشای ویدیوی این مبحث", url: "" },
        },
        {
          questionUrl: "/download.jpg",
          answerUrl: "/download-2.jpg",
          tags: [{ label: "فیزیک" }, { label: "مهم" }, { label: "خیلی سخت" }],
          answer: 1,
          difficulty: 3,
          guide: { label: " تماشای ویدیوی این مبحث", url: "" },
        },
        {
          questionUrl: "/download.jpg",
          answerUrl: "/download-2.jpg",
          tags: [{ label: "فیزیک" }, { label: "مهم" }, { label: "خیلی سخت" }],
          answer: 1,
          difficulty: 3,
          guide: { label: " تماشای ویدیوی این مبحث", url: "" },
        },
        {
          questionUrl: "/download.jpg",
          answerUrl: "/download-2.jpg",
          tags: [{ label: "فیزیک" }, { label: "مهم" }, { label: "خیلی سخت" }],
          answer: 1,
          difficulty: 3,
          guide: { label: " تماشای ویدیوی این مبحث", url: "" },
        },
        {
          questionUrl: "/download.jpg",
          answerUrl: "/download-2.jpg",
          tags: [{ label: "فیزیک" }, { label: "مهم" }, { label: "خیلی سخت" }],
          answer: 1,
          difficulty: 3,
          guide: { label: " تماشای ویدیوی این مبحث", url: "" },
        },
        {
          questionUrl: "/download.jpg",
          answerUrl: "/download-2.jpg",
          tags: [{ label: "فیزیک" }, { label: "مهم" }, { label: "خیلی سخت" }],
          answer: 1,
          difficulty: 3,
          guide: { label: " تماشای ویدیوی این مبحث", url: "" },
        },
        {
          questionUrl: "/download.jpg",
          answerUrl: "/download-2.jpg",
          tags: [{ label: "فیزیک" }, { label: "مهم" }, { label: "خیلی سخت" }],
          answer: 1,
          difficulty: 3,
          guide: { label: " تماشای ویدیوی این مبحث", url: "" },
        },
        {
          questionUrl: "/download.jpg",
          answerUrl: "/download-2.jpg",
          tags: [{ label: "فیزیک" }, { label: "مهم" }, { label: "خیلی سخت" }],
          answer: 1,
          difficulty: 3,
          guide: { label: " تماشای ویدیوی این مبحث", url: "" },
        },
        {
          questionUrl: "/download.jpg",
          answerUrl: "/download-2.jpg",
          tags: [{ label: "فیزیک" }, { label: "مهم" }, { label: "خیلی سخت" }],
          answer: 1,
          difficulty: 3,
          guide: { label: " تماشای ویدیوی این مبحث", url: "" },
        },
        {
          questionUrl: "/download.jpg",
          answerUrl: "/download-2.jpg",
          tags: [{ label: "فیزیک" }, { label: "مهم" }, { label: "خیلی سخت" }],
          answer: 1,
          difficulty: 3,
          guide: { label: " تماشای ویدیوی این مبحث", url: "" },
        },
        {
          questionUrl: "/download.jpg",
          answerUrl: "/download-2.jpg",
          tags: [{ label: "فیزیک" }, { label: "مهم" }, { label: "خیلی سخت" }],
          answer: 1,
          difficulty: 3,
          guide: { label: " تماشای ویدیوی این مبحث", url: "" },
        },
        {
          questionUrl: "/download.jpg",
          answerUrl: "/download-2.jpg",
          tags: [{ label: "فیزیک" }, { label: "مهم" }, { label: "خیلی سخت" }],
          answer: 1,
          difficulty: 3,
          guide: { label: " تماشای ویدیوی این مبحث", url: "" },
        },
        {
          questionUrl: "/download.jpg",
          answerUrl: "/download-2.jpg",
          tags: [{ label: "فیزیک" }, { label: "مهم" }, { label: "خیلی سخت" }],
          answer: 1,
          difficulty: 3,
          guide: { label: " تماشای ویدیوی این مبحث", url: "" },
        },
        {
          questionUrl: "/download.jpg",
          answerUrl: "/download-2.jpg",
          tags: [{ label: "فیزیک" }, { label: "مهم" }, { label: "خیلی سخت" }],
          answer: 1,
          difficulty: 3,
          guide: { label: " تماشای ویدیوی این مبحث", url: "" },
        },
        {
          questionUrl: "/download-1.jpg",
          answerUrl: "/download-2.jpg",
          tags: [{ label: "فیزیک" }, { label: "مهم" }, { label: "خیلی سخت" }],
          answer: 1,
          difficulty: 3,
          guide: { label: " تماشای ویدیوی این مبحث", url: "" },
        },
        {
          questionUrl: "/download.png",
          answerUrl: "/download-2.jpg",
          tags: [{ label: "فیزیک" }, { label: "مهم" }, { label: "خیلی سخت" }],
          answer: 1,
          difficulty: 3,
          guide: { label: " تماشای ویدیوی این مبحث", url: "" },
        },
        {
          questionUrl: "/download-2.jpg",
          answerUrl: "/download-2.jpg",
          tags: [{ label: "فیزیک" }, { label: "مهم" }, { label: "خیلی سخت" }],
          answer: 1,
          difficulty: 3,
          guide: { label: " تماشای ویدیوی این مبحث", url: "" },
        },
      ],
    },
  },
  computed: {
    currentQuestion() {
      return this.questions[this.currentIndex];
    },
  },
  data() {
    const as = {};
    this.questions.forEach((q, i) => {
      as[i] = -1;
    });
    return {
      currentIndex: 0,
      answerSheet: as,
      currentAnswer: -1,
      autoNext: false,
      checkINdex: this.currentIndex,
    };
  },

  watch: {
    currentAnswer() {
      this.answerSheet[this.currentIndex] = this.currentAnswer;
    },
    currentIndex() {
      console.log(this.$refs.scrollHelp.$el.scrollTop);
    },
  },

  methods: {
    onAnswerChanged() {
      if (this.autoNext && this.currentAnswer >= 0) {
        setTimeout(this.next, 1000);
      }
    },
    next() {
      if (this.currentIndex < this.questions.length - 1) {
        this.currentIndex++;
      } else {
        this.currentIndex = 0;
      }
      this.currentAnswer = this.answerSheet[this.currentIndex];
    },
    prw() {
      if (this.currentIndex > 0) {
        this.currentIndex--;
      } else {
        this.currentIndex = this.questions.length - 1;
      }
      this.currentAnswer = this.answerSheet[this.currentIndex];
    },
    subNumHandler(x) {
      this.currentIndex = x;
      this.currentAnswer = this.answerSheet[this.currentIndex];
    },
  },
};
</script>
