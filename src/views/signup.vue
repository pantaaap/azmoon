<template>
  <div class="mx-auto justify-center">
    <v-card class="mx-auto my-16 py-10" max-width="350">
      <template slot="progress">
        <v-progress-linear
          color="deep-purple"
          height="30"
          indeterminate
        ></v-progress-linear>
      </template>
      <v-row class="ma-10 justify-center">
        <v-btn outlined rounded text class="py-5 px-14">
          ثبت نام
        </v-btn>
      </v-row>
      <v-row class="ma-10 justify-center">
        <v-btn outlined rounded text class="pa-5">
          برنامه جامع راهبردی
        </v-btn>
      </v-row>
      <v-row class="ma-10 justify-center">
        <v-btn outlined rounded text class="py-5 px-12">
          پنل کاربری
        </v-btn>
      </v-row>
    </v-card>
  </div>
</template>
