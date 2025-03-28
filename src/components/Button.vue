<template>
  <button :class="buttonTheme">
    <img
      v-if="image"
      :src="image"
      alt=""
      class="imgBtn"
    >
    <span v-html="txtBtn"></span>
  </button>
</template>

<script setup>
import { computed } from 'vue'

const props = defineProps({
  image: {
    type: String,
    default: ""
  },
  txtBtn: {
    type: String,
    default: ""
  },
  theme: {
    type: String,
    default: "green",
    validator: (value) => ["green", "white"].includes(value)
  }
})

const buttonTheme = computed(() => {
  return [
    "buttonTheme", 
    props.theme === "green" ? "buttonGreen" : "buttonWhite"
  ]
})
</script>

<style scoped>
button {
  transition: transform 0.5s ease-in-out;
}
button:hover {
  transform: scale(1.2);
}
.buttonTheme {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 0.5rem;
  /* 8px => 0.5rem, 12px => 0.75rem */
  padding: 0.5rem 0.75rem;
  border-radius: 9999px;
  /* 80px => 5rem */
  height: 5rem;
  /* 239px => 239/16 ≈ 14.94rem */
  width: 14.94rem;
  cursor: pointer;
  font-family: "Nunito", sans-serif;
  font-weight: 900;
  /* 16px => 1rem */
  font-size: 1rem;
}
.buttonGreen {
  background-color: #3ce0a0;
  color: white;
}
.buttonWhite {
  background-color: transparent;
  /* 3px => 3/16 ≈ 0.19rem */
  border: 0.19rem solid #3ce0a0;
  color: #3ce0a0;
}

span {
  white-space: pre-wrap;
}


</style>
