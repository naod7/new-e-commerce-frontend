<script setup>

import Dashboard from "@/components/Dashboard.vue"
import {defineProps} from 'vue'

const {addToCart} = defineProps(['addToCart'])

</script>


<template>
  <v-app>

    <Dashboard
      :addToCart="addToCart"
    />

  </v-app>
</template>



<style scoped>
.index{
  z-index: 9999;
}
</style>