<template>
  <NuxtLayout name="default">
    <v-container fluid>
      <v-row>
        <!-- Hero -->
        <HomeHeroSection class="my-0 my-md-10" />
        <v-row class="align-center">
          <v-col cols="8"> <!-- Colonna per il testo -->
            <h2>
              Non perdere l'occasione di partecipare alla DevFest Basilicata 2025!
              <br>Prenota subito il tuo posto.
            </h2>
          </v-col>
          <v-col cols="4" class="d-flex justify-start"> <!-- Colonna per il pulsante -->
            <v-btn 
              color="primary" 
              @click="openRSVPLink" 
              style="font-size: 1.5em; padding: 15px 30px; height: 60px; min-width: 120px;"
            >
              RSVP
            </v-btn>
          </v-col>
        </v-row>
        <!-- Hero -->

        <!-- Stats -->
        <HomeStats class="my-0 my-md-5" />
        <!-- Stats -->

        <!-- Whats New -->
        <HomeExpectionSection class="mt-md-10" />
        <!-- Whats New -->

        <!-- Technologies -->
        <HomeTechSection class="mb-md-10" />
        <!-- Technologies -->

        <!-- Past DevFest -->
        <HomePastDevFest class="mb-md-10" />
        <!-- Past DevFest -->

        <!-- Sponsors -->
        <HomeSponsorsSection />
        <!-- Sponsors -->

        <!-- Keep in Touch -->
        <HomeCommunityContact />
        <!-- Keep in Touch -->
      </v-row>
    </v-container>
  </NuxtLayout>
</template>

<script setup>
const { mainData } = useJSONData();
definePageMeta({
  layout: false,
});
const openRSVPLink = () => {
  window.open('https://gdg.community.dev/events/details/google-gdg-basilicata-presents-devfest-basilicata-2025/', '_blank');
};
useSeoMeta({
  contentType: "text/html; charset=utf-8",
  title: mainData.eventInfo.name + " | " + mainData.communityName,
  description: mainData.eventInfo.description.short,
  ogLocale:'en_US',
  keywords: mainData.seo.keywords,
  author: "OSS Labs",
  creator: "OSS Labs",
  viewport: "width=device-width, initial-scale=1.0",
  ogTitle: mainData.eventInfo.name + " | " + mainData.communityName,
  ogDescription: mainData.eventInfo.description.short,
  ogImage: `${mainData.seo.hostUrl}/thumbnail.png?auto=format&fit=crop&frame=1&h=512&w=1024`,
  ogUrl: mainData.seo.hostUrl,
  ogType: "website",
  twitterTitle: mainData.eventInfo.name + " | " + mainData.communityName,
  twitterDescription: mainData.eventInfo.description.short,
  twitterImage: `${mainData.seo.hostUrl}thumbnail.png?auto=format&fit=crop&frame=1&h=512&w=1024`,
  twitterCard: "summary_large_image",
});
</script>

<style scoped></style>
