<template>
  
  <Header></Header>
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
import Header from "./components/Header.vue"
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

h1 {
  font-family: "Nunito", sans-serif;
  font-weight: 900;
  font-size: 40px;
  margin-bottom: 1em;
  overflow-wrap: break-word;
}

h2 {
  font-family: "Nunito", sans-serif;
  font-weight: 900;
  font-size: 30px;
  color: #3ce0a0;
}

h3 {
  font-family: "Nunito", sans-serif;
  font-weight: 400;
  font-size: 14px;
  color: #757575;
  text-align: center;
}

/* Main layout */
.mainLayout {
  display: flex;
  width: 100dvw;
  min-height: 100dvh;
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
  background: linear-gradient(#E4F4ED, #F9F9F9);
  max-height: 100dvh;
  height: 322px
}

.listButton {
  display: flex;
  justify-content: space-around;
  gap :1em;
}

.search {
  background-color: white;
  display: flex;
  justify-content: center;
  align-items: center;
}

.searchContainer {
  display: flex;
  align-items: center;
  justify-content: flex-start;
  margin-right : 20%;
  padding-left: 2rem;
  gap: 25%
}

.loupeImg {
  width: 178px;
  height: 178px;
}

.searchContent {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  gap: 1rem;
  width:100%;
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


.divider {
  width: 80%;
  height: 0.0625rem; /* 1px */
  background-color: #e0e0e0;
  margin: 5em auto;
  border: none;
}

.searchResult {
  margin: 7em auto;
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  justify-content: center;
  gap: 2em;
  row-gap: 8em;
  width: 100%;
  max-width: 781px;
  height: auto
}

@media (max-width: 800px) { 
  .mainLayout {
    padding-bottom: 79px
  }
  .actionList {
    height: 70vh
  }
  .listButton {
    flex-direction: column;
    align-items: center;
    gap : 1em
  }
  nav {
    display: none; /* ou visibility: hidden; selon le besoin */
  }
  .loupeImg {
    display : none;
  }
  .searchResult {
    display : flex;
    flex-direction: column;
  }
  .searchContent {
    width: auto;
    height: auto
  }
}
</style>
