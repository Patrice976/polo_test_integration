<template>
    <header>
    <img src="../assets/polo_logo.png" id="logo" alt="logo polo" />
    <div class="userProfileInfo">
      <p>Lola Dufour</p>
      <picture>
        <source media="(max-width: 800px)" srcset="../assets/responsivLola.png">
        <source media="(min-width: 801px)" srcset="../assets/lolapp.png">
        <img src="" alt="photo de profile de lola Dufour" />
      </picture>
      
    </div>
  </header>
</template>

<script setup>
</script>

<style scoped>
header {
  background-color: white;
  display: flex;
  flex-wrap: nowrap;
  justify-content: space-between;
  align-items: center;
  height: 109px
}

.userProfileInfo {
  display: flex;
  align-items: center;
  color: black;
  line-height: 1;
  width: 7.59375rem; /* 121.5px */
  height: 2.25rem; /* 36px */
  font-family: "Nunito", sans-serif;
  font-size: 0.875rem; /* 14px */
  font-weight: 900;
  margin-right : 4em
}

#logo {
  margin-left: 3.75rem; /* 60px */
}

@media(max-width : 800px) {
    .userProfileInfo {
    justify-content: flex-end;
    
  }
  .userProfileInfo p {
    display : none;
  } 
}
</style>