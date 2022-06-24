<template>
  <v-row justify="center" class="mt-10">
    <v-col cols="12" sm="12" md="12">
      <v-card>
        <v-card-title class="headline  pa-4 d-flex justify-center">
          ระบบจัดการฐานข้อมูล
        </v-card-title>
        <v-card-text>
          <v-row justify="center">
            <v-img class="mt-6 mb-6" max-height="300" max-width="250" contain lazy-src="/logo-main.png"
              src="/logo-main.png"></v-img>
          </v-row>
        </v-card-text>
      </v-card>
    </v-col>
  </v-row>
</template>
<script>
export default {
  auth: true,
  name: "IndexPage",
  layout: "dashboard",

};
</script>
