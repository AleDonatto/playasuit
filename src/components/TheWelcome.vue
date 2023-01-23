<template>
  <main-template>
    <template v-slot:content>
      <div class="">
        <v-card>
          <v-carousel hide-delimiters>
            <v-carousel-item
              src="https://upload.wikimedia.org/wikipedia/commons/9/96/Barbados_beach.jpg"
              cover
            ></v-carousel-item>

            <v-carousel-item
              src="https://mindfultravelbysara.com/wp-content/uploads/2021/11/playas-ma%CC%81s-bonitas-de-Me%CC%81xico.jpg"
              cover
            ></v-carousel-item>

            <v-carousel-item
              src="http://c.files.bbci.co.uk/169A5/production/_111118529_gettyimages-1125074301.jpg"
              cover
            ></v-carousel-item>
          </v-carousel>
        </v-card>

        <div class="mt-16">
          <v-row justify="center">
            <v-col cols="12" align="center">
              <h1 class="text-center">Bienvenido a Playa Suit Acapulco</h1>
              <p class="text-body-1 mt-5 text-green font-weight-bold">Busca y reserva la habitaciones que necesites</p>
            </v-col>
          </v-row>
        </div>
      </div>

      <form-reservation></form-reservation>

      <div class="mt-5 mb-16">
        <v-row>
          <v-col cols="5">
            <v-img src="https://b2b2c.cdnpt.com/playa-suites/images/foto-bahia.jpg" max-height="350"></v-img>
          </v-col>
          <v-col cols="6" align-self="center" align="start">
            <h1 class="text-green text.h5">
              Vive la mejor experiencia solo en playa suit acapulco
            </h1>
            <p class="text-body-1">
              Hotel en Acapulco ubicado justo en el centro de la Bahía. Sus dos espectaculares torres de 18 pisos ofrecen 488 habitaciones con balcón privado y una increíble vista a la Bahía, 2 restaurantes y 3 bares para satisfacer tus necesidades culinarias.
            </p>
          </v-col>
        </v-row>
      </div>

    </template>
  </main-template>
</template>

<script setup>
import MainTemplate from './layout/MainTemplate.vue';
import FormReservation from './FormReservation.vue'
</script>

<style scoped>
.bg-color-appbar{
  background-color:#524658 ;
}
</style>