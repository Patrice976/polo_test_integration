<template>
  <nav class="navDesktop">
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

    <div class="footerNav">
      <img src="../assets/PictoTel.png" alt="téléphone">
      <img src="../assets/PictoLettre.png" alt="mail">
    </div>
  </nav>

  
  <nav class="navMobile">
    
    <button class="burger" @click="toggleMenu">
      <img src="../assets/burger.png" alt="Menu">
    </button>

    <div class="score">
      <h3>1740</h3>
      <h4>points</h4>
    </div>
  </nav>

  <div class="overlay" v-if="menuOpen" @click.self="closeMenu">
    <div class="contentOverlay" @click.stop>
      <ul>
        <li>Accueil</li>
        <li>Mes ordonnances</li>
        <li>Mes patients</li>
        <li>Mes pharmacies</li>
        <li>Mes documents</li>
        <li>Mes Pilbeez</li>
        <li>Parrainer un cabinet</li>
      </ul>
    </div>
  </div>
</template>

<script setup>
import {ref} from 'vue'

const menuOpen = ref(false)

function toggleMenu() {
  menuOpen.value = !menuOpen.value
}
function closeMenu() {
  menuOpen.value = false 
}
</script>

<style scoped>

.navMobile{
  display: none;
}
.navDesktop {
  position: relative;
  display: flex;
  flex-direction: column;
  width: 300px;      
  min-height: 100vh;
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

li {
  transition: transform 0.5s ease-in-out;
}
li:hover {
  transform: scale(1.2);
  cursor: pointer;
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
  width: 5px;            
  height: 100%;
  background-color: #fff;
  align-self: flex-start;
}

.footerNav {
  align-self: flex-start;
  display : flex; 
  gap: 1em;
  align-items: center;
  margin-top: auto;
  margin-left : 0;
  margin-bottom: 3em;
  background-color: white;
  width: 139px;    
  height: 60px;
  border-top-right-radius: 100px;
  border-bottom-right-radius: 100px;
}

.footerNav img {
  margin-left: 0.5rem; 
  transition: transform 0.5s ease-in-out;
  cursor: pointer;

}

.footerNav img:hover {
  transform: scale(1.2);
}

@media (max-width: 800px) {


  .navDesktop {
    display: none;
  }

  .spacer {
    height : 79px
  }
  .navMobile {
    display: flex ; 
    position: fixed;
    bottom: 0;
    left: 0;
    width: 100%;
    height: 79px;
    background-color: #3ce0a0;
    justify-content: space-between;
    align-items: center;
    padding: 0 1rem;
    z-index: 9999;;
  }

  .burger {
    background: none;
    border: none;
    cursor: pointer;
  }

  .score {
    background-color: #FFD900 ;
    padding: 0.5rem 1rem;
  }
  .score h3 {
    font-family: "Nunito", sans-serif;
    font-weight: 900;
    font-size: 30px;
    color: #fff;
  }
  .score h4 {
    font-family: "Nunito", sans-serif;
    font-weight: 900;
    font-size: 16px;
    color: black;
  }

  .overlay {
  position: fixed;
  top: 0; 
  left: 0;
  width: 100%;
  height: 100%;
  background: #3ce0a1f6; 
  display: flex;
  justify-content: center;
  align-items: center;
  z-index: 9999; 
  
  font-size: 18px;
  font-family: "Nunito", sans-serif;
  font-weight: 900;
  color: white;

  }

  .overlay ul {
    display: flex;
    flex-direction: column;
    gap: 3em;
    line-height: 173%;         
    list-style: none;
  }
}

</style>
