<template>
  <v-container fluid class="google-font" >
    <v-row justify="center" align="center" class="px-2" >
      <v-col md="12" class="pa-md-10 pa-5" style="background-color: white; border-radius: 15px">
        <p
          class="google-font gdg-h1 mb-2 grey--text text--darken-4"
          style="font-size: 220%"
        >
          ¿Que me voy a encontrar?
        </p>
        <p>
          Un evento anual organizado por Google Developers Group en todo el mundo.
          para acercar la tecnología a los desarrolladores. es todo el dia
          conferencia de desarrolladores donde nuestro objetivo es centrarnos en múltiples tecnologías
          a través de charlas relámpago, sesiones, talleres, etc.
        </p>
        <v-container fluid class="px-0">
          <v-row>
            <v-col
              md="4"
              sm="4"
              cols="12"
              v-for="(item, index) in devfestInfo.what_to_expect"
              :key="index"
            >
              <div
                class="pa-md-6 pa-4"
                style="background-color: #E8F1FB;border-radius: 12px;"
              >
                <p style="font-size: 20px; font-weight: 600" class="mt-4">
                  {{ item.label }}
                </p>
                <p>{{ item.value }}</p>
              </div>
            </v-col>
          </v-row>
        </v-container>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
import devfestJSON from "@/assets/data/devfests.json";
export default {
  name: "OverviewComponent",
  data: () => ({
    devfestInfo: devfestJSON,
  }),
};
</script>

<style>
</style>