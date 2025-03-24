<script setup>

</script>

<template>
  <header>
  <img src="./assets/polo_logo.png" id="logo" alt="logo polo">
  <div class="userProfileInfo">
    <p>Lola Dufour</p>
    <img src="./assets/lolapp.png" alt="photo de profile de lola Dufour">
  </div>
  </header>

  <div class="mainLayout">
    <nav>
      <ul>
        <li>Acceuil</li>
        <li>Mes ordonnances</li>
        <li id="patients">Mes patients </li> 
          <ul>
            <li>Tous les patients</li>
            <li>Patients en attente</li>
            <li>Patients archivés</li>
          </ul>
        <li>Mes pharmacies</li>
        <li>Mes documents</li>
        <li>Mes Pilbeez</li>
        <li>Parrainer un cabinet</li>
      </ul>
    </nav>

    <main>
      <section class="actionList">
        <h1>Les patients du cabinet</h1>
      </section>
      <section class="search"></section>
      <section class="searchResult"></section>
    </main>
</div>
</template>

<style scoped>

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
  font-family: 'simply_rounded' 

}

#logo {
  margin-left : 60px;

}

.mainLayout {
  display: flex;
  width : 100dvw
}

nav {
  display : flex;
  flex-direction: column;
  height: 100dvh;
  width: 300px;
  align-items: center;
  font-family: 'simply_rounded';
  font-size: 18px;
  background-color: #3ce0a0  ;
  color : white
}

main {
  flex : 1
}

nav>ul {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  height: 25%; 
  gap:32px;
  margin-top : 65px;
  list-style : none
}

#patients{
  display:flex ;
  color:black;
  margin-bottom: 0;
}

nav ul ul {
  display: flex;
  flex-direction: column;
  gap: 6px;
  list-style: none;
  
}

nav ul ul li {
  font-size: 12px;
  gap: 6px
}

.actionList {
  clip-path: polygon(0% 0%, 100% 0%, 100% 75%, 51% 75%, 46% 83%, 41% 75%, 0% 75%);
  height: 282px;
  background: linear-gradient(#E4F4ED,#F9F9F9);
 
}

.search {
  background-color : white;
  height : 288px;
}


</style> 
