<script setup lang="ts"></script>

<template>
  <v-container class="address-container">
    <v-card class="pa-6 mx-auto" max-width="750px" elevation="5">
      <!-- Étapes -->
      <v-row class="justify-center">
        <v-col cols="12" class="text-center">
          <h2 class="text-h6 font-weight-bold">Livraison de mon objet</h2>
        </v-col>
        <v-col cols="12" class="d-flex justify-center align-center steps">
          <!-- Étape 1 (ADRESSE) : en bleu -->
          <v-avatar size="40" class="bg-blue accent-4 text-white font-weight-bold"> 1 </v-avatar>
          <span class="mx-2 font-weight-bold blue--text text-darken-4">ADRESSE</span>
          <!-- Étape 2 (EXPÉDITION) grisée -->
          <v-avatar size="40" class="bg-grey-lighten-3">2</v-avatar>
          <span class="mx-2 grey--text">EXPÉDITION</span>
          <!-- Étape 3 (PAIEMENT) grisée -->
          <v-avatar size="40" class="bg-grey-lighten-3">3</v-avatar>
          <span class="mx-2 grey--text">PAIEMENT</span>
        </v-col>
      </v-row>

      <!-- Titre -->
      <h3 class="text-subtitle-1 font-weight-bold mt-4">ADRESSE DE LIVRAISON</h3>

      <!-- Formulaire -->
      <v-form>
        <v-text-field label="Entreprise" outlined dense></v-text-field>

        <v-row>
          <v-col cols="6">
            <v-text-field label="Prénom *" outlined dense></v-text-field>
          </v-col>
          <v-col cols="6">
            <v-text-field label="Nom *" outlined dense></v-text-field>
          </v-col>
        </v-row>

        <v-text-field label="Email *" outlined dense></v-text-field>

        <v-row>
          <v-col cols="6">
            <v-select
              :items="['France métropolitaine', 'Belgique', 'Suisse']"
              label="Pays"
              outlined
              dense
            ></v-select>
          </v-col>
          <v-col cols="6">
            <v-text-field label="Adresse *" outlined dense></v-text-field>
          </v-col>
        </v-row>

        <v-text-field label="Adresse (ligne 2)" outlined dense></v-text-field>

        <v-row>
          <v-col cols="6">
            <v-text-field label="Code postal *" outlined dense></v-text-field>
          </v-col>
          <v-col cols="6">
            <v-text-field label="Ville *" outlined dense></v-text-field>
          </v-col>
        </v-row>

        <v-row>
          <v-col cols="6">
            <v-select :items="['+33', '+32', '+41']" label="Indicatif" outlined dense></v-select>
          </v-col>
          <v-col cols="6">
            <v-text-field label="Téléphone *" outlined dense></v-text-field>
          </v-col>
        </v-row>

        <v-checkbox label="Instructions de livraison (interphone, étage...)"></v-checkbox>

        <v-checkbox label="Adresse de facturation différente"></v-checkbox>

        <!-- Boutons bas -->
        <v-row class="mt-4">
          <v-col cols="6">
            <v-btn variant="outlined" color="grey darken-1" block>Retour</v-btn>
          </v-col>
          <v-col cols="6">
            <v-btn color="blue accent-4" dark block>Suivant</v-btn>
          </v-col>
        </v-row>
      </v-form>
    </v-card>
    <!-- Petites bulles décoratives -->
    <div class="bubble bubble1"></div>
    <div class="bubble bubble2"></div>
  </v-container>
</template>

<style scoped>
.address-container {
  /* Couleur pastel en fond */
  background-color: #e2f3f5;
  min-height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
  position: relative;
}

.steps {
  margin-top: 0.5rem;
}

.bubble {
  width: 100px;
  height: 100px;
  background-color: rgba(255, 255, 255, 0.5);
  border-radius: 50%;
  position: absolute;
  z-index: 0;
}
.bubble1 {
  top: 5%;
  left: 10%;
}
.bubble2 {
  bottom: 10%;
  right: 8%;
}
</style>
