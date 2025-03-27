<template>
    <div class="card" :id="theme">
      <img :src="profilpic" :alt="nom" class="patientPic">
      <div class="card-body">
        <h1>{{ name }}</h1>
        <h2>{{ age }}</h2>
        <hr class="divider">
        <div class="more-info">
          <span><img src="../assets/Phone.png" alt="téléphone"> 04 77 36 65 95</span>
          <span><img src="../assets/Letter.png" alt="mail"> cecilemoulin@gmail.com</span>
          <span><img src="../assets/Localisation.png" alt="lieu"> 16 rue Maurice Bouchor 68007 Lyon</span>
          <span><img src="../assets/more.png" alt="plus">voir ses ordonnances</span>
        </div>
      </div>
    </div>
</template>

<script setup>
import {defineProps} from "vue" 

const props = defineProps({
    profilpic: {
      type: String,
      default: ""
    },
    name: {
      type: String,
      default: ""
    },
    age: {
      type: String, 
      defautlt : ""
    },
    theme : {
      type: String,
      default: "green",
      validator: (value) => ["green", "white"].includes(value)
    }
    })


</script>

<style scoped>

.card {
  position: relative; 
  width : 200px ; 
  height : 245px;
  display: flex; 
  flex-direction: column;
  font-family: "Nunito", sans-serif;
  font-weight: 900;
  font-size: 12px;
  margin : auto;
  padding: 32px;
  border-radius : 10px;
}

.card h1 {
  font-family: "Nunito", sans-serif;
  font-weight: 900;
  font-size: 16px;
  text-align: center;
  color: #3CE0A0;  
}
.card h2 {
  font-family: "Nunito", sans-serif;
  font-weight: 400;
  font-size: 14px;
  text-align: center;
}
.more-info {
  display: flex; 
  flex-direction: column;
  justify-content: flex-start;
  align-items: flex-start;
  gap: 1em;
  margin: auto;
}
.card span {
  display: grid;
  grid-template-columns: 20px 1fr;
  gap: 1em;
  width: 100%
} 

.divider {
  width : 80%;
  height: 1px;
  background-color: #e0e0e0;
  margin : 1rem
}

#green {
background-color: #e4f4ed ;
border : none;
}

#white {
  background-color: white;
  border : solid 3px #3CE0A0
}

.patientPic {
position: absolute;
top: -30% ;
left: 27%; 

}

</style>