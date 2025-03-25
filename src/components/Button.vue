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
  import { defineProps, computed } from 'vue'
  
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
  .buttonTheme {
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 0.5rem;
    padding: 8px 12px;
    border-radius: 9999px;
    height: 80px;
    width: 239px;
    cursor: pointer;
    font-family: "Nunito", sans-serif;
    font-weight: 900;
    font-size: 16px; 
   
  }
  
  .buttonGreen {
    background-color: #3ce0a0;
    color: white;
  }
  
  .buttonWhite {
    background-color: transparent;
    border: 3px solid #3ce0a0;
    color: #3ce0a0;
  }

  span {
    white-space: pre-wrap;
  }
  
 
  </style>
  