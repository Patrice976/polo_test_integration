
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
        :image="pictoWaitingPatient " ></CustomButton>
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
      <section class="search"></section>
      <section class="searchResult"></section>
    </main>
</div>
</template>

<script setup>
import CustomButton from "./components/Button.vue"
import Navigation from "./components/Navigation.vue"
import pictoAddPatient from "./assets/Picto_ajout_patient.png"
import pictoWaitingPatient from "./assets/Picto_patient_attente.png"
import pictoArchived from "./assets/Picto_archives.png"
import pictoHelper from "./assets/Picto_aidant.png"
</script>

<style scoped>
h1{
  font-family: "Nunito", sans-serif;
  font-weight: 900;
  font-size: 40px;
  margin-bottom: 1em;
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
  width : 100dvw
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
}



</style> 
