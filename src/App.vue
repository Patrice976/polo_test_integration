
<template>
  <head>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Nunito:ital,wght@0,200..1000;1,200..1000&display=swap" rel="stylesheet">
</head>
  <header>
  <img src="./assets/polo_logo.png" id="logo" alt="logo polo">
  <div class="userProfileInfo">
    <p>Lola Dufour</p>
    <img src="./assets/lolapp.png" alt="photo de profile de lola Dufour">
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
        :image="pictoAddPatient" ></CustomButton>
        <CustomButton
        theme="green"
        txtBtn="Patients <br>en attente"
        :image="pictoWaitingPatient "></CustomButton>
        <CustomButton
        theme="white"
        txtBtn="Patients <br>archivés"
        :image="pictoArchived " ></CustomButton>
        <CustomButton
        theme="white"
        txtBtn="Voir les <br>aidants"
        :image="pictoHelper " ></CustomButton>
      </div>
      </section>
      <section class="search">
        <div class="searchContainer">
          <img src="./assets/Loupe.png" alt="image loupe" class="loupeImg">
          <div class="searchContent">
            <h2> Recherchez un patient </h2>
            <h3>Entrez les première lettres de nom du patient que vous recherchez </h3>
            <form @submit.prevent="handleSearch" class="searchFrom">
            <input type="text"
            v-model="searchQuery"
            placeholder="écrivez ici"
            class="search-input" />
          </form>
          </div>
        </div>
      </section>
      <hr class="divider">
      <section class="searchResult">
      <Patient
      v-for="patient in data" 
      :key="patient.id"
      :name="patient.nom"
      :age="patient.age"
      :profilpic="patient.photo"
      :theme="(patient.id % 2 === 0) ? 'white' : 'green'" 
      ></Patient>
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
</script>

<style scoped>
h1{
  font-family: "Nunito", sans-serif;
  font-weight: 900;
  font-size: 40px;
  margin-bottom: 1em;
}

h2{
  font-family: "Nunito", sans-serif;
  font-weight: 900;
  font-size: 30px;
  color: #3CE0A0
}

h3{
  font-family: "Nunito", sans-serif;
  font-weight: 400;
  font-size: 14px;
  color: #757575
}


header{
  background-color: white;
  
  display: flex;
  flex-wrap: nowrap;
  justify-content: space-between;
  align-items: center;
  height : 109px;
  

}
.userProfileInfo {
  display :flex;
  align-items: center;
  color : black;
  line-height: 1;
  width: 121.5px;
  height: 36px;
  margin-right: 60px;
  font-family: "Nunito", sans-serif;
  font-size: 14px;
  font-weight: 900; 

}

#logo {
  margin-left : 60px;

}

.mainLayout {
  display: flex;
  width : 100dvw;
  min-height: 100dvh;
  align-items: stretch;
}


main {
  flex : 1
}


.actionList {
  display : flex;
  flex-direction: column;
  align-items: center;
  padding-top: 52px;
  clip-path: polygon(0% 0%, 100% 0%, 100% 75%, 55% 75%, 50% 83%, 45% 75%, 0% 75%);
  height: 322.38px;
  background: linear-gradient(#E4F4ED,#F9F9F9);
 
}

.listButton {
  width: 80%;
  display : flex ;
  justify-content: space-between;
}

.search {
  background-color : white;
  height : 288px;
  display: flex; 
  justify-content: center;
  align-items: center;
  
}

.searchContainer{
  display:flex;
  align-items: center;
  justify-content: flex-start;
  margin: 0 auto;   /* centre le conteneur sur la page */
  padding-left: 2rem;

}


.loupeImg {
  width: 178px;
  height: 178px
}

.search-input {
  width: 359px;
  height: 60px;
  padding: 0.5rem 1rem;
  border-radius: 9999px; 
  border: 1px solid #ccc;
  font-size: 1rem;
  font-family: "Nunito", sans-serif;
  font-weight: 900;
  font-size: 16px;
  text-align: center;
}


.searchContent {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  width: 540px;
  height: 161px; 
}

.divider {
  width : 80%;
  height: 1px;
  background-color: #e0e0e0;
  margin : 0 auto
}

.searchResult {
  margin: auto;
  display: grid;
  grid-template-columns: repeat(3, 1fr);             
  gap : 1em;
  width:781px;
  height:865px;

}


</style> 
