<template>
  <v-container fluid class="pa-0 ma-0">
    <v-row
      v-for="(item, index) in sponsorsData"
      :key="index"
      class="google-font mb-5 mt-0"
    >
      <v-col md="12" cols="12" class="mb-n1"
        ><b>{{ item.category_name }}</b></v-col
      >
      <v-col
        md="2"
        cols="6"
        sm="3"
        v-for="(sponsor, indexp) in item.sponsors"
        :key="indexp"
      >
        <v-row
          style="background-color: #F3F3F3; border-radius: 15px;border: 1px solid black;"
          class="fill-height align-center ma-0"
        >
          <v-col>

          <ClientOnly>
            <v-tooltip location="bottom" :key="indexp">
              <template v-slot:activator="{ props }">
                <a aria-label="sponsor name" :href="sponsor.link" target="_blank" v-bind="props">
                  <v-img alt="sponsor-logo" :src="getSponsorLogo(sponsor.logo)"></v-img>
                </a>
              </template>
              <span>{{ sponsor.name }}</span>
            </v-tooltip>
          </ClientOnly>
          </v-col>
        </v-row>
      </v-col>
    </v-row>
  </v-container>
</template>

<script setup>
const { sponsorsData } = useJSONData();
const getSponsorLogo = (logo) => {
  if (logo.startsWith('http')) {
    return logo;
  }
  return `/img/sponsors/${logo}`;
};
</script>

<style>
</style>
