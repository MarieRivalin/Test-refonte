<script setup lang="ts"></script>

<template>
  <!-- Conteneur principal, fond dégradé léger -->
  <v-container class="choice-container py-10">
    <v-card class="pa-6 mx-auto" max-width="700" elevation="5">
      <!-- Titre principal, centré -->
      <v-card-title class="d-flex justify-center title-text"> Votre objet oublié </v-card-title>

      <v-divider class="my-3" color="blue-darken-2" />

      <v-row>
        <!-- Colonne gauche : image 200x200, centrée -->
        <v-col cols="12" sm="4" class="d-flex justify-center align-center">
          <v-img
            src="https://via.placeholder.com/200?text=OBJET+TROUVE"
            alt="objet trouvé"
            width="200"
            height="200"
            class="shadow-lg"
            cover
          />
        </v-col>

        <!-- Colonne droite : texte et boutons -->
        <v-col cols="12" sm="8" class="text-center">
          <div class="body-1">
            <p class="mb-3">
              <strong>Monsieur HUA XXX,</strong>
              nous avons retrouvé un objet qui pourrait vous appartenir :
              <strong>Câble, Chargeur</strong>.
            </p>
            <p>Nos équipes l'ont mis de côté. Comment pouvons-nous vous le restituer ?</p>
          </div>

          <!-- Boutons : le premier en bleu foncé, les autres en mode "outlined" -->
          <v-row dense class="mt-4 button-group">
            <!-- 1er bouton (bleu) -->
            <v-col cols="12">
              <v-btn block color="blue darken-2" dark class="my-btn"> Envoyer à une adresse </v-btn>
            </v-col>

            <!-- 2e, 3e, 4e boutons (blancs / outline) -->
            <v-col cols="12">
              <v-btn block variant="outlined" color="blue darken-2" class="my-btn">
                Récupérer sur place
              </v-btn>
            </v-col>
            <v-col cols="12">
              <v-btn block variant="outlined" color="blue darken-2" class="my-btn">
                Abandonner mon objet
              </v-btn>
            </v-col>
            <v-col cols="12">
              <v-btn block variant="outlined" color="blue darken-2" class="my-btn">
                Cet objet ne m'appartient pas
              </v-btn>
            </v-col>
          </v-row>
        </v-col>
      </v-row>
    </v-card>
  </v-container>
</template>

<style scoped>
.choice-container {
  /* Petit dégradé clair, d'un gris bleuté vers un blanc */
  background: linear-gradient(135deg, #f0f4fd 0%, #e5ecfa 100%);
  min-height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
}

.title-text {
  font-size: 1.4rem;
  font-weight: bold;
  color: #1a237e;
}

.my-btn {
  text-transform: none;
  font-weight: 600;
  border-radius: 6px;
}
</style>
