<template>
  <!-- headers -->
  <div>
    <v-card color="amber darken-3" dark shaped>
      <v-row class="justify-space-between align-center d-flex align-center">
        <v-col cols="1" class="mr-n0 px-n5">
          <v-card
            class="justify-center align-center d-flex align-center mr-4"
            color="amber darken-3"
            elevation="0"
          >
            <h3>مرحله</h3></v-card
          >
        </v-col>
        <v-col cols="1" class="mr-n5 px-n5">
          <v-card
            class="justify-center align-center d-flex align-center"
            color="amber darken-3"
            elevation="0"
          >
            <h3>تاریخ</h3></v-card
          >
        </v-col>
        <v-col cols="1" class="mr-n3 px-3">
          <v-card
            class="justify-center align-center d-flex align-center mr-5"
            color="amber darken-3"
            elevation="0"
            ><h4 class="text-center">دفترچه سوال</h4></v-card
          >
        </v-col>
        <v-col cols="3" class="mr-n3">
          <v-card
            class="justify-center align-center d-flex align-center"
            color="amber darken-3"
            elevation="0"
          >
            <h3>پاسخنامه تشریحی \ تصویری</h3></v-card
          >
        </v-col>
        <v-col cols="1" class="mr-n5">
          <v-card
            class="justify-center align-center d-flex align-center"
            color="amber darken-3"
            elevation="0"
            ><h3>کارنامه ها</h3></v-card
          >
        </v-col>
        <v-col cols="1" class="mr-n5">
          <v-card
            class="justify-center align-center d-flex align-center"
            color="amber darken-3"
            elevation="0"
          >
            <h4>کلید آزمون</h4></v-card
          >
        </v-col>
        <v-col cols="1" class="mr-n5">
          <v-card
            class="justify-center align-center d-flex align-center"
            color="amber darken-3"
            elevation="0"
          >
            <h4 class="text-center">اشتباهات و نزده ها</h4></v-card
          >
        </v-col>
        <v-col cols="1" class="mr-n5">
          <v-card
            class="justify-center align-center d-flex align-center text-center"
            color="amber darken-3"
            elevation="0"
          >
            <h4 class="text-center">شروع آزمون</h4>
          </v-card>
        </v-col>
        <v-col cols="1" class="mr-n5">
          <v-card
            class="justify-center align-center d-flex align-center ml-3"
            color="amber darken-3"
            elevation="0"
            ><h3>وضعیت</h3></v-card
          >
        </v-col>
      </v-row>
    </v-card>

    <!-- 
       #
       #
       #
       #
       #
       actual ones -->

    <v-row class="justify-space-between align-center d-flex align-center">
      <v-col cols="1" class="mr-n0 px-n5">
        <v-card class="justify-center align-center d-flex align-center mr-4">
          <h3>مرحله</h3></v-card
        >
      </v-col>
      <v-col cols="1" class="mr-n5 px-n5">
        <v-card class="justify-center align-center d-flex align-center">
          <h3>تاریخ</h3></v-card
        >
      </v-col>
      <v-col cols="1" class="mr-n3 px-3">
        <v-card class="justify-center align-center d-flex align-center mr-5"
          ><h4 class="text-center">دفترچه سوال</h4></v-card
        >
      </v-col>
      <v-col cols="3" class="mr-n3">
        <v-card class="justify-center align-center d-flex align-center">
          <h3>پاسخنامه تشریحی \ تصویری</h3></v-card
        >
      </v-col>
      <v-col cols="1" class="mr-n5">
        <v-card class="justify-center align-center d-flex align-center"
          ><h3>کارنامه ها</h3></v-card
        >
      </v-col>
      <v-col cols="1" class="mr-n5">
        <v-card class="justify-center align-center d-flex align-center">
          <h4>کلید آزمون</h4></v-card
        >
      </v-col>
      <v-col cols="1" class="mr-n5">
        <v-card class="justify-center align-center d-flex align-center">
          <h4 class="text-center">اشتباهات و نزده ها</h4></v-card
        >
      </v-col>
      <v-col cols="1" class="mr-n5">
        <v-card class="justify-center align-center d-flex align-center">
          <h4 class="text-center">شروع آزمون</h4>
        </v-card>
      </v-col>
      <v-col cols="1" class="mr-n5">
        <v-card class="justify-center align-center d-flex align-center ml-3"
          ><h3>وضعیت</h3></v-card
        >
      </v-col>
    </v-row>
  </div>
</template>