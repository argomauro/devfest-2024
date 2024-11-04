<template>
  <v-container fluid class="pa-0 ma-0" v-if="props.data">
    <v-row
      justify-center
      align="center"
      v-for="(item, index) in props.data['schedule']"
      :key="index"
      class="pa-0 my-0 row-border-white"
    >
      <v-col md="2" cols="3" class="text-right my-0 py-0">
        <p style="font-size: 110%" class="mb-0 google-font">
          {{ formatTime(item.startTime) }} <!-- Modificato -->
        </p>
        <p style="font-size: 70%" class="ma-0 google-font">
          {{ formatTime(item.endTime) }} <!-- Modificato -->
        </p>
        <p class="mt-1 google-font" style="font-size: 60%">
          <b style="color: grey">CET (+01:00)</b>
        </p>
      </v-col>
      <v-col
        class="my-0 schedule-details-white col-border-white"
        cols="9"
        md="10"
      >
        <ClientOnly>
          <CommonScheduleDialoge :data="getSessionData(item.session)" />
        </ClientOnly>
      </v-col>
    </v-row>
  </v-container>
</template>

<script setup>
const { sessionsData } = useJSONData();

const props = defineProps({
  data: {
    type: Object,
    default: {},
  },
});

// Funzione per formattare il tempo nel formato 12 ore (AM/PM)
const formatTime = (time) => {
  const [hours, minutes] = time.split(':');
  const parsedHours = parseInt(hours, 10);
  const isPM = parsedHours >= 12;
  const formattedHours = parsedHours % 12 || 12; // Converte in formato 12 ore
  const period = isPM ? 'PM' : 'AM';
  
  return `${formattedHours}:${minutes} ${period}`;
};

const getSessionData = (id) => {
  return sessionsData.filter((sd) => sd.id == id)[0];
};
</script>

<style scoped>
.schedule-details-white:hover {
  background: #fafafa;
}
.row-border-white {
  border-bottom: 1px solid #e0e0e0;
}
.col-border-white {
  border-left: 1px solid #e0e0e0;
}
</style>
