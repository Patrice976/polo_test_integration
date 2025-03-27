<template>
  <head>
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <link rel="preconnect" href="https://fonts.googleapis.com" />
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
    <link
      href="https://fonts.googleapis.com/css2?family=Nunito:ital,wght@0,200..1000;1,200..1000&display=swap"
      rel="stylesheet"
    />
  </head>
  <header>
    <img src="./assets/polo_logo.png" id="logo" alt="logo polo" />
    <div class="userProfileInfo">
      <p>Lola Dufour</p>
      <img src="./assets/lolapp.png" alt="photo de profile de lola Dufour" />
    </div>
  </header>

  <div class="mainLayout">
    <Navigation></Navigation>
    <main>
      <section class="actionList">
        <h1>Les patients du cabinet</h1>
        <div class="listButton">
          <CustomButton
            theme="green"
            txtBtn="Ajouter <br>un patient"
            :image="pictoAddPatient"
          />
          <CustomButton
            theme="green"
            txtBtn="Patients <br>en attente"
            :image="pictoWaitingPatient"
          />
          <CustomButton
            theme="white"
            txtBtn="Patients <br>archivés"
            :image="pictoArchived"
          />
          <CustomButton
            theme="white"
            txtBtn="Voir les <br>aidants"
            :image="pictoHelper"
          />
        </div>
      </section>
      <section class="search">
        <div class="searchContainer">
          <img src="./assets/Loupe.png" alt="image loupe" class="loupeImg" />
          <div class="searchContent">
            <h2>Recherchez un patient</h2>
            <h3>
              Entrez les première lettres de nom du patient<br />
              que vous recherchez
            </h3>
            <form @submit.prevent="handleSearch" class="searchForm">
              <input
                type="text"
                v-model="searchQuery"
                placeholder="écrivez ici"
                class="search-input"
              />
            </form>
          </div>
        </div>
      </section>
      <hr class="divider" />
      <section class="searchResult">
        <Patient
          v-for="patient in data"
          :key="patient.id"
          :name="patient.nom"
          :age="patient.age"
          :profilpic="patient.photo"
          :theme="(patient.id % 2 === 0) ? 'white' : 'green'"
        />
      </section>
    </main>
  </div>
</template>

<script setup>
import CustomButton from "./components/Button.vue"
import Navigation from "./components/Navigation.vue"
import Patient from "./components/Patient.vue"
import patientData from "./assets/data/PatientData.json"
import pictoAddPatient from "./assets/Picto_ajout_patient.png"
import pictoWaitingPatient from "./assets/Picto_patient_attente.png"
import pictoArchived from "./assets/Picto_archives.png"
import pictoHelper from "./assets/Picto_aidant.png"

const data = patientData
// N'oublie pas de déclarer searchQuery et handleSearch si nécessaire :
import { ref } from "vue"
const searchQuery = ref("")
function handleSearch() {
  console.log("Recherche :", searchQuery.value)
}
</script>

<style scoped>
/* On part d'une base de 16px => 1rem = 16px */

/* Titres principaux */
h1 {
  font-family: "Nunito", sans-serif;
  font-weight: 900;
  font-size: 2.5rem; /* 40px */
  margin-bottom: 1em;
}

h2 {
  font-family: "Nunito", sans-serif;
  font-weight: 900;
  font-size: 1.875rem; /* 30px */
  color: #3ce0a0;
}

h3 {
  font-family: "Nunito", sans-serif;
  font-weight: 400;
  font-size: 0.875rem; /* 14px */
  color: #757575;
  text-align: center;
}

/* Header */
header {
  background-color: white;
  display: flex;
  flex-wrap: nowrap;
  justify-content: space-between;
  align-items: center;
  height: 6.8125rem; /* 109px */
}

.userProfileInfo {
  display: flex;
  align-items: center;
  color: black;
  line-height: 1;
  width: 7.59375rem; /* 121.5px */
  height: 2.25rem; /* 36px */
  margin-right: 3.75rem; /* 60px */
  font-family: "Nunito", sans-serif;
  font-size: 0.875rem; /* 14px */
  font-weight: 900;
}

#logo {
  margin-left: 3.75rem; /* 60px */
}

/* Main layout */
.mainLayout {
  display: flex;
  width: 100vw;
  min-height: 100vh;
  align-items: stretch;
}

main {
  flex: 1;
}

/* Section ActionList */
.actionList {
  display: flex;
  flex-direction: column;
  align-items: center;
  padding-top: 3.25rem; /* 52px */
  clip-path: polygon(0% 0%, 100% 0%, 100% 75%, 55% 75%, 50% 83%, 45% 75%, 0% 75%);
  height: 20.15rem; /* 322.38px */
  background: linear-gradient(#E4F4ED, #F9F9F9);
}

.listButton {
  width: 80%;
  display: flex;
  justify-content: space-between;
}

/* Section Search */
.search {
  background-color: white;
  /* On laisse la hauteur s'ajuster au contenu */
  display: flex;
  justify-content: center;
  align-items: center;
}

.searchContainer {
  display: flex;
  align-items: center;
  justify-content: flex-start;
  margin: 0 auto;
  padding-left: 2rem;
}

.loupeImg {
  width: 11.125rem; /* 178px */
  height: 11.125rem;
}

.searchContent {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  gap: 1rem;
  width: 33.75rem; /* 540px */
  height: 10.0625rem; /* 161px */
}

.searchForm {
  /* Ajoute des styles si nécessaire pour le formulaire */
}

.search-input {
  width: 22.4375rem; /* 359px */
  height: 3.75rem; /* 60px */
  padding: 0.5rem 1rem;
  border-radius: 9999px;
  border: 0.0625rem solid #ccc; /* 1px */
  font-family: "Nunito", sans-serif;
  font-weight: 900;
  font-size: 1rem; /* 16px */
  text-align: center;
  margin: 1em;
}

/* Divider */
.divider {
  width: 80%;
  height: 0.0625rem; /* 1px */
  background-color: #e0e0e0;
  margin: 5em auto;
  border: none;
}

/* Section SearchResult */
.searchResult {
  margin: auto;
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 1em;
  width: 48.8125rem; /* 781px */
  height: 54.0625rem; /* 865px */
}

/* Media Query pour les écrans <= 850px */
@media (max-width: 53.125rem) {  /* 850px / 16 = 53.125rem */
  .actionList {
    height: 100vh;
  }
  .listButton {
    flex-direction: column;
    align-items: center;
  }
}
</style>
