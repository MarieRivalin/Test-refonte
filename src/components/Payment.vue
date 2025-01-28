<script setup lang="ts">
import { ref, computed } from 'vue'

const shippingCost = ref(9.31)
const serviceFee = ref(6.0)
const totalCost = computed(() => (shippingCost.value + serviceFee.value).toFixed(2))

const paymentMode = ref('card')

const cardNumber = ref('')
const cardExpiry = ref('')
const cardCvc = ref('')
const cardCountry = ref('France')
</script>

<template>
  <v-container class="payment-container py-10">
    <v-card class="pa-6 mx-auto" max-width="750px" elevation="5">
      <!-- Étapes -->
      <v-row class="justify-center">
        <v-col cols="12" class="text-center">
          <h2 class="text-h6 font-weight-bold white--text">Livraison de mon objet</h2>
        </v-col>
        <v-col cols="12" class="d-flex justify-center align-center">
          <!-- Étape 1 & 2 -> check vert / Étape 3 -> violet -->
          <v-avatar size="40" class="bg-success text-white">
            <v-icon>mdi-check</v-icon>
          </v-avatar>
          <span class="mx-2 text-white">ADRESSE</span>

          <v-avatar size="40" class="bg-success text-white">
            <v-icon>mdi-check</v-icon>
          </v-avatar>
          <span class="mx-2 text-white">EXPÉDITION</span>

          <v-avatar size="40" class="bg-deep-purple accent-4 text-white">3</v-avatar>
          <span class="mx-2 deep-purple--text text-accent-4">PAIEMENT</span>
        </v-col>
      </v-row>

      <!-- Récapitulatif -->
      <v-row class="mt-4">
        <v-col cols="12">
          <h3 class="text-subtitle-1 font-weight-bold white--text">Récapitulatif</h3>
          <div class="text-body-1 mb-2 white--text">
            <div>Expédition : {{ shippingCost }} €</div>
            <div>Participation frais PeeK’in : {{ serviceFee }} €</div>
            <strong>Total : {{ totalCost }} €</strong>
          </div>
          <small class="grey--text text-lighten-2"> Module sécurisé SSL par Stripe </small>
        </v-col>
      </v-row>

      <!-- Formulaire de paiement -->
      <v-form class="mt-3">
        <!-- Radio (carte / paypal) -->
        <v-radio-group v-model="paymentMode" color="deep-purple accent-2">
          <v-radio label="Carte bancaire" value="card" class="white--text" />
          <v-radio label="PayPal" value="paypal" class="white--text" />
        </v-radio-group>

        <!-- Bloc carte si selected=card -->
        <div v-if="paymentMode === 'card'">
          <v-text-field
            v-model="cardNumber"
            label="Numéro de carte"
            outlined
            dense
            color="deep-purple accent-2"
          ></v-text-field>
          <v-row>
            <v-col cols="6">
              <v-text-field
                v-model="cardExpiry"
                label="Date d'expiration (MM / AA)"
                outlined
                dense
                color="deep-purple accent-2"
              ></v-text-field>
            </v-col>
            <v-col cols="6">
              <v-text-field
                v-model="cardCvc"
                label="Code de sécurité (CVC)"
                outlined
                dense
                color="deep-purple accent-2"
              ></v-text-field>
            </v-col>
          </v-row>
          <v-select
            v-model="cardCountry"
            :items="['France', 'Belgique', 'Suisse']"
            label="Pays"
            outlined
            dense
            color="deep-purple accent-2"
          ></v-select>
        </div>

        <div v-else class="white--text">
          <p>Vous serez redirigé(e) vers PayPal pour finaliser le paiement.</p>
        </div>

        <v-row class="mt-4">
          <v-col cols="6">
            <v-btn variant="outlined" color="grey lighten-2" class="white--text" block>
              Retour
            </v-btn>
          </v-col>
          <v-col cols="6">
            <v-btn block color="deep-purple accent-4" dark> Payer {{ totalCost }} € </v-btn>
          </v-col>
        </v-row>
      </v-form>
    </v-card>
  </v-container>
</template>

<style scoped>
.payment-container {
  background: linear-gradient(120deg, #2c3e50 0%, #4c3c6f 100%);
  min-height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
}
</style>
