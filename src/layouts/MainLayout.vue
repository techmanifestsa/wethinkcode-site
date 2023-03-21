<template>
  <q-layout view="lHh Lpr lFf">
    <q-header elevated class="bg-white">
      <q-banner
        v-if="covidBanner"
        dense
        inline-actions
        class="covid-banner text-white text-center"
      >
        Stay informed about COVID-19:
        <a href="https://sacoronavirus.co.za/" class="text-white q-ml-sm"
          >Visit SA's Dept of Health Online Resource Portal</a
        >
        <template v-slot:action>
          <q-btn @click="dismissCovidBanner" flat color="white" label="Dismiss" />
        </template>
      </q-banner>

        <q-toolbar class="q-pa-lg wrapper">

          <q-item clickable v-ripple to="/"><q-img to="/" clickable class="wtc-logo" src="../assets/wtc-logo.png" :ratio="16 / 9" /></q-item>

          <q-item clickable v-ripple to="/push"><q-toolbar-title class="color-wtc q-ml-lg"> Push Notification Triggers </q-toolbar-title></q-item>
        </q-toolbar>
    </q-header>

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>
import { defineComponent, ref } from "vue";

export default defineComponent({
  name: "MainLayout",


  setup() {
    const covidBanner = ref(true);

    return {
      covidBanner,
      dismissCovidBanner() {
        covidBanner.value = !covidBanner.value;
      },

    };
  },
});
</script>
<style scoped>
.covid-banner {
  background-color: #4b82c2;
}
.color-wtc {
  color: #4b82c2;
}
.wtc-logo {
  width: 75px;
  height: 75px;
}
</style>
