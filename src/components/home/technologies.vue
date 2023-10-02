<template>
    <v-container fluid class="google-font">
      <v-row justify="center" align="center"  class="px-2">
        <v-col md="8" cols="12" sm="12" class="pa-md-10 pa-5" style="background-color: white;border-radius: 15px" >
          <p class="google-font gdg-h1 mb-2 grey--text text--darken-4">
            Tecnologías que podrás encontrar
          </p>
          <p>En las diferentes charlas y talleres que tendremos en el evento, verás de manos de expertos, las últimas novedades e información de tecnologías de Google</p>
          <v-container fluid>
            <v-row justify="start" align="start">
              <v-col md="1" sm="2" cols="3" v-for="(item, index) in techs" :key="index">
                <a :href="item.link" target="_blank">
                  <v-avatar color="white" size="60">
                    <v-img :src="item.logo"></v-img>
                  </v-avatar>
                </a>
              </v-col>
            </v-row>
          </v-container>
        </v-col>
        <v-col md="4" cols="12" sm="12">
          <div class="pa-md-10 pa-5"  style="background-color: #D8F0FE;border-radius: 15px" >
            <p style="font-size: 320%;font-weight: bold;line-height: 60px;">¡Únete con nosotros! </p>
            <p style="font-size: 160%;">{{ communityInfo.community_name }}</p>

            <v-btn rounded depressed :href="communityInfo.community_url" target="_blank" color="primary">Join Now</v-btn>
          </div>
        </v-col>
      </v-row>
    </v-container>
  </template>
  
  <script>
  import communityJSON from "@/assets/data/community.json";
  export default {
    name: 'TechFocues',
    data: () => ({
      communityInfo: communityJSON,
      techs: [
        {
          name: "Android",
          link: "https://developer.android.com/",
          logo: "https://io.google/2022/app/images/android-logo.svg",
        },
        {
          name: "Firebase",
          link: "https://firebase.google.com/",
          logo: "https://io.google/2022/app/images/firebase-logo.svg",
        },
        {
          name: "Flutter",
          link: "https://flutter.dev/",
          logo: "https://io.google/2022/app/images/flutter-logo.svg",
        },
        {
          name: "Google Assistant & Smart Home",
          link: "https://developers.google.com/assistant",
          logo: "https://io.google/2022/app/images/googleassistant-logo.svg",
        },
        {
          name: "Google Maps",
          link: "https://developers.google.com/maps",
          logo: "https://io.google/2022/app/images/googlemaps-logo.svg",
        },
        {
          name: "Material Design",
          link: "https://material.io/design",
          logo: "https://io.google/2022/app/images/materialdesign-logo.svg",
        },
        {
          name: "TensorFlow",
          link: "https://www.tensorflow.org/",
          logo: "https://io.google/2022/app/images/machinelearning-logo.svg",
        },
        {
          name: "Web",
          link: "https://developers.google.com/web",
          logo: "https://io.google/2022/app/images/web-logo.svg",
        },
      ],
    }),
  };
  </script>
  
  <style>
  </style>