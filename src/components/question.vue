<template>
  <v-card
    class="mx-auto my-12"
    width="100%"
    color="grey lighten-5"
    elevation="0"
  >
    <v-img
      height="250"
      width="100%"
      src="https://images.squarespace-cdn.com/content/v1/5ea237e587e03021f9ef8cc2/1591321482139-5N4EC0SIATZQYDTX8I3G/ke17ZwdGBToddI8pDm48kCLbhA7m7AmYv7-6E_H7lbB7gQa3H78H3Y0txjaiv_0fDoOvxcdMmMKkDsyUqMSsMWxHk725yiiHCCLfrh8O1z4YTzHvnKhyp6Da-NYroOW3ZGjoBKy3azqku80C789l0ouw-8l5B_J38LMU7OZFvYdoh1CoK9or-QWSHGWhYAjrn6y9-oC5sPHSqhi8nMLAnA/Question-mark.jpg"
      contain
    ></v-img>

    <v-divider class="mx-4 my-5"></v-divider>
    <v-row class="mx-5 justify-center">
      <v-chip-group
        v-model="selection"
        active-class="indigo darken-3 white--text"
        column
      >
        <v-chip class="px-md-10 px-7 py-4 title font-weight-black">الف</v-chip>

        <v-chip class="px-md-10 px-8 py-4 title font-weight-black">ب</v-chip>

        <v-chip class="px-md-10 px-8 py-4 title font-weight-black">ج</v-chip>

        <v-chip class="px-md-10 px-8 py-4 title font-weight-black">د</v-chip>
      </v-chip-group>
    </v-row>
    <v-divider class="mx-4 my-5"></v-divider>

    <v-card-actions>
      <v-btn width="48%"> سوال بعدی</v-btn>
      <v-btn width="48%"> سوال قبلی</v-btn></v-card-actions
    >
  </v-card>
</template>