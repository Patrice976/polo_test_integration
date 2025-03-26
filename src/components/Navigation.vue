<template>
  <nav>
    <ul>
      <li>Acceuil</li>
      <li>Mes ordonnances</li>
      <li id="patients">
        <div class="patient_li">
          <img
            src="../assets/Picto_Patient.png"
            alt=""
            class="logoPatient"
          />Mes patients<img
            src="../assets/ArrowUp.png"
            alt=""
            class="vectorUp"
          />
        </div>
        <ul>
          <li>Tous les patients</li>
          <li>Patients en attente</li>
          <li>Patients archivés</li>
        </ul>
      </li>
      <li>Mes pharmacies</li>
      <li>
        <div class="document">
          Mes documents <img src="../assets/ArrowDown.png" alt="" />
        </div>
      </li>
      <li>Mes Pilbeez</li>
      <li>Parrainer un cabinet</li>
    </ul>
  </nav>
</template>

<script setup></script>

<style scoped>
nav {
  position: relative;
  display: flex;
  flex-direction: column;
  width: 300px;
  align-items: center;
  font-size: 18px;
  font-family: "Nunito", sans-serif;
  font-weight: 900;
  background-color: #3ce0a0;
  color: white;
}

nav > ul {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  height: 25%;
  gap: 32px;
  margin-top: 65px;
  list-style: none;
}

#patients {
  color: black;
  margin-bottom: 0;
}

#patients ul {
  color: white;
  font-size: 12px;
}

nav ul ul {
  display: flex;
  flex-direction: column;
  gap: 6px;
  line-height: 173%;
  list-style: none;
}

nav ul ul li {
  font-size: 12px;
  gap: 6px;
  margin-left: 35px;
}

.patient_li {
  position: relative;
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 6px;
}
.patient_li::before {
  content: "";
  position: absolute;
  left: -3.53dvw;
  top: 0;
  bottom: 0;
  width: 5px;
  background-color: #fff;
}

.logoPatient {
  height: 14px;
  width: 12px;
}

.document {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.white-bar {
  width: 5px;
  height: 100%;
  background-color: #fff;
  align-self: flex-start;
}
</style>
