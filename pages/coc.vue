<template>
  <NuxtLayout name="default">
    <v-container fluid class="mt-5">
      <v-row>
        <v-col md="12">
          <h1>Code of Conduct</h1>
          <p>
            Tutti i partecipanti all'evento DevFest 2024, inclusi i partecipanti online, lo staff dell'evento e i relatori, devono rispettare la seguente politica:
            <ul>
              <li>Rispetto e professionalità: Trattare tutti con cortesia e rispetto.</li>
              <li>Comportamento appropriato: Evitare linguaggio e comportamenti inappropriati.</li>
              <li>Inclusività: Favorire un ambiente accogliente per tutti, indipendentemente da razza, genere, orientamento sessuale, disabilità o altro.</li>
              <li>Segnalazione di problemi: Eventuali violazioni della politica devono essere segnalate allo staff dell'evento.</li>
              <li>La mancata osservanza di queste linee guida può comportare l'espulsione dall'evento.</li>
          </ul>
          </p>

          <v-container fluid class="ma-0 pa-0 mt-8">
            <v-row align="start" justify-start>
              <v-col
                md="4"
                cols="12"
                v-for="(item, index) in cocData"
                :key="index"
              >
                <p class="google-font" style="font-size: 1.2em">
                  <b>{{ item.name }}</b>
                </p>
                <p class="google-font mt-3" style="font-size: 100%">
                  {{ item.des }}
                </p>
              </v-col>
            </v-row>
          </v-container>
        </v-col>
      </v-row>
    </v-container>
  </NuxtLayout>
</template>

<script setup>
const { cocData, mainData } = useJSONData();

definePageMeta({
  layout: false,
});

useSeoMeta({
  contentType: "text/html; charset=utf-8",
  title:
    "Code of Conduct - " +
    mainData.eventInfo.name +
    " | " +
    mainData.communityName,
  description: mainData.eventInfo.description.short,
  keywords: mainData.seo.keywords,
  ogLocale:'en_US',
  author: "OSS Labs",
  creator: "OSS Labs",
  viewport: "width=device-width, initial-scale=1.0",
  ogTitle:
    "Code of Conduct - " +
    mainData.eventInfo.name +
    " | " +
    mainData.communityName,
  ogDescription: mainData.eventInfo.description.short,
  ogImage: `${mainData.seo.hostUrl}/thumbnail.png?auto=format&fit=crop&frame=1&h=512&w=1024`,
  ogUrl: mainData.seo.hostUrl,
  ogType: "website",
  twitterTitle:
    "Code of Conduct - " +
    mainData.eventInfo.name +
    " | " +
    mainData.communityName,
  twitterDescription: mainData.eventInfo.description.short,
  twitterImage: `${mainData.seo.hostUrl}thumbnail.png?auto=format&fit=crop&frame=1&h=512&w=1024`,
  twitterCard: "summary_large_image",
});
</script>

