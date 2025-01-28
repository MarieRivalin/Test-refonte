<script setup lang="ts">
import { ref } from 'vue'

const selectedOffer = ref('eco')
</script>
<template>
  <v-container class="offer-container py-10">
    <v-card class="pa-6 mx-auto" max-width="750px" elevation="5">
      <!-- Étapes -->
      <v-row class="justify-center">
        <v-col cols="12" class="text-center">
          <h2 class="text-h6 font-weight-bold">Livraison de mon objet</h2>
        </v-col>
        <v-col cols="12" class="d-flex justify-center align-center">
          <!-- Étape 1 : check vert -->
          <v-avatar size="40" class="bg-success text-white">
            <v-icon>mdi-check</v-icon>
          </v-avatar>
          <span class="mx-2 font-weight-bold green--text text-darken-3">ADRESSE</span>

          <!-- Étape 2 : active => orange -->
          <v-avatar size="40" class="bg-orange darken-3 text-white font-weight-bold"> 2 </v-avatar>
          <span class="mx-2 font-weight-bold orange--text text-darken-3"> EXPÉDITION </span>

          <!-- Étape 3 : grisé -->
          <v-avatar size="40" class="bg-grey-lighten-3">3</v-avatar>
          <span class="mx-2 grey--text">PAIEMENT</span>
        </v-col>
      </v-row>

      <!-- Sous-titre -->
      <v-row class="mt-4">
        <v-col cols="12">
          <h3 class="text-subtitle-1 font-weight-bold teal--text text-darken-2">
            Mode de livraison
          </h3>
        </v-col>
      </v-row>

      <!-- Choix (radio group) -->
      <v-form>
        <v-radio-group v-model="selectedOffer" color="teal darken-2">
          <!-- Économique -->
          <v-radio value="eco">
            <template #label>
              <strong>Économique : 15.31 €</strong>
              <p class="text-body-2 mb-0">
                par Colissimo : livraison estimée sous 5 jours ouvrés ...
              </p>
              <ul class="text-body-2 my-1">
                <li>✔ Suivi en ligne</li>
                <li>✘ Indemnisation en cas de perte</li>
              </ul>
            </template>
          </v-radio>

          <!-- Express -->
          <v-radio value="express">
            <template #label>
              <strong>Express : 43.07 €</strong>
              <p class="text-body-2 mb-0">
                par Chronopost : livraison estimée sous 2 jours ouvrés ...
              </p>
              <ul class="text-body-2 my-1">
                <li>✔ Suivi en ligne</li>
                <li>✔ Indemnisation en cas de perte (avec supplément)</li>
              </ul>
            </template>
          </v-radio>
        </v-radio-group>
      </v-form>

      <!-- Boutons bas -->
      <v-row class="mt-4">
        <v-col cols="6">
          <v-btn variant="outlined" color="grey darken-1" block> Retour </v-btn>
        </v-col>
        <v-col cols="6">
          <v-btn block color="teal darken-2" dark> Suivant </v-btn>
        </v-col>
      </v-row>
    </v-card>
  </v-container>
</template>

<style scoped>
.offer-container {
  background: linear-gradient(120deg, #a1c4fd 0%, #c2e9fb 100%);
  min-height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
}
</style>
