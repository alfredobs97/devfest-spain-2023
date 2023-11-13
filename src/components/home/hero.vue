<template>
  <v-container fluid class="my-0">
    <!-- Row 1 -->
    <v-row justify="center" align="center">
      <v-col md="12">
        <v-img
          max-height="380"
          style="border-radius: 15px"
          :src="require('@/assets/img/cover.png')"
        ></v-img>
      </v-col>
    </v-row>
    <!-- Row 1 -->

    <!-- Row 2 -->
    <v-row justify="center" align="center" class="my-md-10 my-4">
      <v-col md="8" cols="12" order-md="1" order-sm="2" class="py-md-10">
        <p
          class="google-font gdg-h1 mb-4 grey--text text--darken-4"
          style="font-size: 200%; line-height: 40px"
        >
          DevFest 2023 <br />
          <span style="color: #4285f4">{{ communityInfo.community_name }}</span>
        </p>
        <p class="google-font mt-3 mb-0" style="font-size: 19px">
          <v-icon>mdi-calendar-month</v-icon> {{ devfestInfo.date }}
        </p>
        <p class="google-font mb-0" style="font-size: 19px">
          <v-icon>mdi-clock-time-eight-outline</v-icon> {{ devfestInfo.time }}
        </p>
        <p class="google-font mt-0" style="font-size: 19px">
          <v-icon>mdi-map-marker</v-icon> Andalucía Lab
        </p>
        <p
          class="google-font text--secondary"
          style="font-weight: 500; font-size: 18px"
        >
          {{ devfestInfo.desc.short }}
        </p>
        <p
          class="google-font text--secondary"
          style="font-weight: 500; font-size: 18px"
        >
        El lugar: Andalucía Lab
Un espacio excepcional en el corazón de la Costa del Sol, Andalucía Lab será la sede de DevFest GDG Spain 2023
        </p>
        <v-btn
          dark
          depressed
          rounded
          color="#4285F4"
          class="mr-2"
          :href="devfestInfo.registration.link"
          v-if="devfestInfo.registration.status == 1"
          target="_blank"
          >Regístrate
        </v-btn>
        <v-btn
          dark
          depressed
          rounded
          color="#00000" 
          href="https://www.google.com/maps/place/Andaluc%C3%ADa+Lab/@36.4992076,-4.7991027,17z/data=!3m2!4b1!5s0xd7320bba2831c01:0x5a9de8cfe0c6b31b!4m6!3m5!1s0xd72d7fdc4eb1883:0xcd07fb9f70251ef7!8m2!3d36.4992033!4d-4.7965278!16s%2Fg%2F1t_h_b9f?entry=ttu"
          v-if="devfestInfo.registration.status == 1"
          target="_blank"
          >Cómo llegar
        </v-btn>
      </v-col>
      <v-col md="4" cols="12" order-md="2" order-sm="1" class="google-font">
        <v-container fluid class="px-0">
          <v-row>
            <v-col
              md="4" cols="4" sm="2"
              v-for="(item, index) in devfestInfo.stats.slice(0, 6)"
              :key="index"
            >
              <div style="background-color: #e9f1fb;border-radius: 15px;" class="text-center py-5">
                <p
                  class="mb-0"
                  style="font-size: 200%; font-weight: 900; color: #4285f4"
                >
                  {{ item.value }}
                </p>
                <p class="my-1">{{ item.name }}</p>
              </div>
            </v-col>
          </v-row>
        </v-container>
      </v-col>
    </v-row>
    <!-- Row 2 -->

  </v-container>
</template>

<script>
import devfestJSON from "@/assets/data/devfests.json";
import communityJSON from "@/assets/data/community.json";
export default {
  name: "HeroComponent",
  data: () => ({
    loading: true,
    communityInfo: communityJSON,
    devfestInfo: devfestJSON,
  }),
  methods: {},
};
</script>

<style>
</style>