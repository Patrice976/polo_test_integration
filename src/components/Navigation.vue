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
  width: 18.75rem;            /* 300px */
  align-items: center;
  font-size: 1.125rem;         /* 18px */
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
  gap: 2rem;                /* 32px */
  margin-top: 4.06rem;        /* 65px approx. */
  list-style: none;
}

nav > ul > li {
  width: 100%;
}

#patients {
  color: black;
  margin-bottom: 0;
}

#patients ul {
  color: white;
  font-size: 0.75rem;         /* 12px */
}

nav ul ul {
  display: flex;
  flex-direction: column;
  gap: 0.375rem;            /* 6px */
  line-height: 173%;         /* reste en pourcentage */
  list-style: none;
}

nav ul ul li {
  font-size: 0.75rem;         /* 12px */
  gap: 0.375rem;            /* 6px */
  margin-left: 2.19rem;       /* 35px */
}

.patient_li {
  position: relative;
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 0.375rem;    /* 6px */
}

.patient_li::before {
  content: "";
  position: absolute;
  left: 0;
  top: 0;
  bottom: 0;
  width: 0.31rem;            /* 5px */
  background-color: #fff;
  transform: translateX(-3.4em);
}

.logoPatient {
  height: 0.875rem;          /* 14px */
  width: 0.75rem;            /* 12px */
}

.document {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.white-bar {
  width: 0.31rem;            /* 5px */
  height: 100%;
  background-color: #fff;
  align-self: flex-start;
}
</style>
