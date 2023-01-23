<template>
    <div>
        <v-row justify="center">
            <v-col cols="10">
                <v-card elevation="5">
                    <v-form class="mx-5 my-10">
                        <v-row>
                            <v-col cols="12" lg="3" md="3">
                                <label for="" class="text-body-2">Fecha de Llegada:</label>
                                <v-text-field type="date" variant="outlined"></v-text-field>
                            </v-col>
                            <v-col cols="12" lg="3" md="3">
                                <label for="" class="text-body-2">Fecha Salida:</label>
                                <v-text-field type="date" variant="outlined"></v-text-field>
                            </v-col>
                            <v-col cols="12" md="3" lg="3" rounded>
                                <label for="" class="text-body-2">Personas:</label>
                                <v-menu v-model="popover" :close-on-content-click="false" location="bottom">
                                    <template v-slot:activator="{props}">
                                        <!--<v-text-field v-bind="props" class="" label="Personas:" variant="outlined"></v-text-field>-->
                                        <v-card min-height="55" v-bind="props" variant="outlined">
                                            <p class="py-3 px-3">{{reservation.adulto + reservation.menores}} personas en {{reservation.habitacion}} {{ reservation.habitacion > 1 ? 'Habitación': 'habitaciónes'}}</p>
                                        </v-card>
                                    </template>

                                    <v-card min-width="520" class="mt-3">
                                        <div class="ma-5">
                                            <v-row >
                                                <v-col cols="12" lg="4" md="3">
                                                    <label for="" class="text-caption">Habitaciones</label>
                                                    <v-select v-model="reservation.habitacion" variant="outlined" :items="totalHabitaciones" item-value="num" item-title="num"></v-select>
                                                </v-col>
                                                <v-col cols="12" lg="8" md="7">
                                                    <v-row no-gutters justify="start">
                                                        <v-col cols="4"></v-col>
                                                        <v-col cols="4"><p class="text-caption">Adultos:</p></v-col>
                                                        <v-col cols="4"><p class="text-caption">Menores (0-17):</p></v-col>
                                                    </v-row>
                                                    <v-row no-gutters v-for="(items, index) in reservation.habitacion" :key="index" justify="end">
                                                        <v-col cols="4" align-self="center" align="end">
                                                            <p class="text-caption px-2">Hab. {{index+1}}:</p>
                                                        </v-col>
                                                        <v-col cols="4" align-self="center" class="pr-1">
                                                            <v-select class="text-caption" variant="outlined" :items="totalAdultos" item-value="adu" item-title="adu"></v-select>
                                                        </v-col>
                                                        <v-col cols="4" class="pl-2" align-self="center">
                                                            <v-select class="text-caption" variant="outlined" :items="totalMenores" items-value="men" item-title="men" ></v-select>
                                                        </v-col>
                                                    </v-row>
                                                </v-col>
                                            </v-row>
                                            <v-divider />
                                        </div>
                                    </v-card>
                                </v-menu>
                            </v-col>
                            <v-col cols="12" lg="3" md="3" align-self="center">
                                <v-btn class="text-white text-none" color="#fb528f" @click="showHabitaciones  = !showHabitaciones">
                                    <span class="font-weight-bold">Ver Disponibilidad</span>
                                </v-btn>
                            </v-col>
                        </v-row>
                    </v-form>
                </v-card>
            </v-col>
        </v-row>

        <div class="mt-10" v-if="showHabitaciones">
            <v-row justify="center">
                <v-col cols="10">
                    <h1 class="text-green font-weight-bold text-body-1">Habitaciones</h1>
                    <v-card elevation="5" class="my-5" outlined tile v-for="(item, index) in 3" :key="'test'+index">
                        <template v-slot:title>
                            <span class="font-weight-bold text-h5">Super saver</span>
                        </template>
                        <template v-slot:text>
                            <v-row justify="center">
                                <v-col cols="4" align="start">
                                    <v-img src="https://img.cdnpth.com/media/14Dlz9VtpjzzEHkVh87hb7nsrq8=/720x480/04/67/82/04678267.jpg" max-height="320" cover></v-img>
                                </v-col>
                                <v-col cols="8" align="start">
                                    <p class="text-body">Entrada: 15:00</p>
                                    <p class="text-body">Salida: 12:00</p>
                                    <p class="text-body">Vista: Ninguna o Calle</p>

                                    <p class="text-h6 font-weight-bold mt-10">Amenidades</p>
                                    <p class="text-body">2 Matrimoniales, Aire acondicionado, Terraza, Teléfono de marcado directo, Llave electrónica, Baño privado con bañera y ducha, Caja de seguridad, Sala </p>
                                </v-col>
                            </v-row>
                        </template>
                    </v-card>
                </v-col>
            </v-row>
        </div>
    </div>
</template>

<script setup>
import { reactive, ref } from 'vue';

const popover = ref(false)
const showHabitaciones = ref(false)

const reservation = reactive({
    fechaLlegada: '',
    fechaSalida: '',
    adulto: 2,
    menores: 0,
    habitacion: 1,
    personas: [],
    edadMenores: []
})

const testHabitaciones = ref([])

const totalHabitaciones = ref([
    {num: 1},
    {num: 2},
    {num: 3},
    {num: 4},
    {num: 5},
    {num: 6},
    {num: 7},
    {num: 8},
    {num: 9},
    {num: 10},
])

const totalMenores = ref([
    {men: 1},
    {men: 2},
    {men: 3},
    {men: 4},
    {men: 5},
    {men: 6},
])

const totalAdultos = ref([
    {adu: 1},
    {adu: 2},
    {adu: 3},
    {adu: 4},
    {adu: 5},
    {adu: 6},
    {adu: 7},
    {adu: 8},
])
</script>

<style scoped>
</style>