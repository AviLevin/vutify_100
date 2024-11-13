<template>
  <!-- Custom Vuetify button with yellow background and custom slot content -->
  <v-btn
    :color="color"
    :elevation="elevation"
    :rounded="rounded"
    class="custom-btn"
  >
    <slot />
  </v-btn>
</template>

<script setup>
import { defineProps } from 'vue';

// Define props for customization
defineProps({
  color: {
    type: String,
    default: 'light-blue', // Default color for button background
  },
  elevation: {
    type: Number,
    default: 2,
  },
  rounded: {
    type: Boolean,
    default: 'lg',
  },
});
</script>

<style scoped>
/* Custom styles */
.custom-btn {
  /*background-color: yellow !important;*/
  color: black !important; /* Ensures readable text on yellow */
  font-weight: bold;
  font-size: medium;
}
</style>
