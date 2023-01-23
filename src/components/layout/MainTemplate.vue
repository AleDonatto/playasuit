<template>
    <v-app>
        <v-app-bar elevation="2" class="py-5 bg-color-appbar" color="#524658">
            <v-row>
                <v-col cols="3">
                    <v-img :src="playasuit" max-height="60"></v-img>
                </v-col>
                <v-col cols="9">
                    <RouterLink to="/">Home</RouterLink>
                </v-col>
            </v-row>
        </v-app-bar>
        <!--<v-navigation-drawer></v-navigation-drawer>-->

        <v-main>
            <slot name="content"></slot>

            <v-footer app bottom padless class="mt-16" absolute>
                2023 — Vuetify, LLC
            </v-footer>
        </v-main>
    </v-app>
</template>

<script setup>
import playasuit from '../../assets/images/logo-playa.png'
import { RouterLink } from 'vue-router';
</script>

<style scoped>
.bg-color-appbar{
  background-color:#524658 ;
}
</style>