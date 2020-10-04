<template>
  <v-simple-table dense>
    <template v-slot:default>
      <thead>
        <tr>
          <th class="text-center">جدول تراز و رتبه کل در این آزمون</th>
          <th class="text-center"></th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="item in numbers" :key="item.name">
          <td>{{ item.name }}</td>
          <td>{{ item.num }}</td>
        </tr>
      </tbody>
    </template>
  </v-simple-table>
</template>

<script>
export default {
  data() {
    return {
      numbers: [
        {
          name: "تراز دروس عمومی",
          num: 159000,
        },
        {
          name: "تراز دروس اختصاصی",
          num: 159000,
        },
        {
          name: "تراز کل",
          num: 159000,
        },
        {
          name: "رتبه کشوری (بدون سهمیه)",
          num: 159000,
        },
      ],
    };
  },
};
</script>