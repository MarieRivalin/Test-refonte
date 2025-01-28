<script setup lang="ts"></script>

<template>
  <!-- Grand conteneur avec un dégradé en arrière-plan -->
  <v-container class="choice-container py-10">
    <v-card class="pa-6 mx-auto" max-width="700" elevation="5">
      <!-- Titre principal -->
      <v-card-title class="d-flex justify-center title-text"> Votre objet oublié </v-card-title>

      <v-divider class="my-3" color="deep-purple-darken-2"></v-divider>

      <v-row>
        <!-- Image à gauche, sur desktop -->
        <v-col cols="12" sm="4" class="d-flex justify-center align-center">
          <v-img
            src="https://via.placeholder.com/200x200.png?text=Objet+Trouvé"
            alt="objet trouvé"
            class="rounded-xl shadow-lg"
            width="200"
            height="200"
            cover
          ></v-img>
        </v-col>

        <!-- Texte explicatif à droite -->
        <v-col cols="12" sm="8">
          <div class="body-1 text-justify">
            <p class="mb-3">
              <strong>Monsieur HUA XXX,</strong> nous avons retrouvé un objet qui pourrait vous
              appartenir&nbsp;: <strong>Câble, Chargeur</strong>.
            </p>
            <p>Nos équipes l'ont mis de côté. Comment pouvons-nous vous le restituer ?</p>
          </div>

          <!-- Groupe de boutons avec des couleurs plus tranchées -->
          <v-row dense class="mt-4 button-group">
            <v-col cols="12">
              <v-btn block color="deep-purple accent-4" dark class="my-btn">
                Envoyer à une adresse
              </v-btn>
            </v-col>
            <v-col cols="12">
              <v-btn block color="pink lighten-2" dark class="my-btn"> Récupérer sur place </v-btn>
            </v-col>
            <v-col cols="12">
              <v-btn block color="cyan darken-1" dark class="my-btn"> Abandonner mon objet </v-btn>
            </v-col>
            <v-col cols="12">
              <v-btn block color="blue-grey darken-1" dark class="my-btn">
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
  background: linear-gradient(135deg, #fbc2eb 0%, #a18cd1 100%);
  min-height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
}

.title-text {
  font-size: 1.4rem;
  font-weight: bold;
  color: #4a148c;
}

.my-btn {
  text-transform: none;
  font-weight: 600;
}
</style>
