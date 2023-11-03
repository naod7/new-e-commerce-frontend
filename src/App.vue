<script setup>
import {ref} from 'vue'
import Navbar from "@/components/Navbar.vue"

//import SideBar from "@/components/SideBar.vue"

const cart = ref({})
function addToCart(title, quantity){
  if(!cart.value[title]){
    cart.value[title] = 0
  }

  cart.value[title]+= quantity

}

</script>


<template>

  <v-app>

    <v-main >

      <Navbar
              :cart="cart"
            />
      <router-view
      :addToCart="addToCart"
      :cart="cart"
      />
    </v-main>
  </v-app>
</template>

