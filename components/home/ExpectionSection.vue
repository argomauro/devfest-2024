<template>
  <v-container fluid>
    <v-row>
      <v-col md="12" sm="12">
        <h1>Cosa aspettarsi</h1>
        <p>
          Unisciti a una giornata di formazione e networking con workshop pratici,
          sessioni tecniche su tecnologie Google, la possibilità di connettersi con esperti e appassionati del settore
          e molto altro! Scopri, impara, e collabora per creare insieme!
        </p>
      </v-col>
      <v-col
        md="4"
        sm="4"
        cols="12"
        v-for="(item, index) in mainData.eventInfo.whatToExpect"
        :key="index"
      >
        <div
          style="
            background-color: #eeeeee;
            border-radius: 20px;
            border: 1.5px solid black;
          "
        >
          <v-img
            :src="getImage(index + 1)"
            width="140"
            alt="image"
            class="float-right mr-5"
          ></v-img>
          <div class="pa-8">
            <h2>{{ item.title }}</h2>
            <p style="font-size: 95%">
              {{ item.description }}
            </p>
          </div>
        </div>
      </v-col>
    </v-row>
  </v-container>
</template>

<script setup>
import img1 from "@/assets/img/section-elements/se-1.svg";
import img2 from "@/assets/img/section-elements/se-2.svg";
import img3 from "@/assets/img/section-elements/se-3.svg";

const { mainData } = useJSONData();
const getImage = (index) => {
  if (index == 1) return img1;
  if (index == 2) return img2;
  if (index == 3) return img3;
};
</script>

<style>
</style>
