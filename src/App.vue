<script setup lang="ts">
import Choice from './components/Choice.vue'
import Adress from './components/Adress.vue'
import Offer from './components/Offer.vue'
import Payment from './components/Payment.vue'
</script>

<template>
  <v-img
    class="contain"
    height="200"
    src="https://via.placeholder.com/1024x200.png?text=Banniere+Peu+Importe"
  />

  <v-container fluid>
    <Choice />
    <Adress />
    <Offer />
    <Payment />
  </v-container>
</template>

<style></style>
