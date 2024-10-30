<template>
  <v-container fluid >
    <v-row>
      <v-col md="12">
        <h1>I nostri sponsor</h1>
        <p>Sponsor dedicati a creare un'esperienza straordinaria!</p>
         <p class="text-subtitle-1 font-weight-medium mt-2">
          Con il patrocinio della Città di Matera
        </p>

        <!-- Aggiunta delle immagini sotto il testo del patrocinio -->
        <v-row class="mt-4" justify="center">
          <v-col cols="12" md="6">
            <v-img
              src="/img/logoMatera1.jpg"
              alt="Logo Città di Matera 1"
              max-width="300"
              class="mx-auto"
            />
          </v-col>
          <v-col cols="12" md="6">
            <v-img
              src="/img/logoMatera2.jpg"
              alt="Logo Città di Matera 2"
              max-width="300"
              class="mx-auto"
            />
          </v-col>
        </v-row>
        <v-container fluid class="pa-0 mt-4">
          <CommonSponsorInfo />
        </v-container>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
</script>

<style>
</style>
