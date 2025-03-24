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

  <nav>
    <ul>
      <li></li>
    </ul>
  </nav>

  <main>
    <section class="actionList"></section>
    <section class="search"></section>
    <section class="searchResult"></section>
  </main>
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


</style>
