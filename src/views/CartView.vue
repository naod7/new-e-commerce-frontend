
<script setup>
    import "@/assets/style.scss"
    import {defineProps} from 'vue'
    const {cart} = defineProps(['cart'])
    import products from '@/products.json'


    function toggleMenu(){
        return toggle.value = !toggle.value
    }

    /*function getPrice(name){
      const product = products.find((p)=>{
        return p.name === name
      })
      return product.Price
    }*/



</script>

<template>
    <v-col cols="12" sm="4" class="pl-0">
        <v-card height="250px" tile flat color="#6857E1">
          <v-row>
            <div class="cart">
                <h1 class="cart-title spread">
                <span>
                    Cart
                    <i class="icofont-cart-alt icofont-1x"></i>
                </span>
                <button class="cart-close" @click="toggleMenu">&times;</button>
                </h1>

                <div class="cart-body">
                <table class="cart-table">
                    <thead>
                    <tr>
                        <th><span class="sr-only">Product Image</span></th>
                        <th>Product</th>
                        <th>Price</th>
                        <th>Qty</th>
                        <th>Total</th>
                        <th><span class="sr-only">Actions</span></th>
                    </tr>
                    </thead>
                    <tbody>
                    <tr v-for="(quantity, key, i) in cart" :key="i">

                        <td>{{ key }}</td>
                        <!--<td>${{  getPrice(key)  }}</td>--->
                        <td class="center">{{ quantity }}</td>
                        <!--<td>${{ quantity * getPrice(key) }}</td>--->
                        <td class="center">
                        <button class="btn btn-light cart-remove" @click="removeCart">
                            &times;
                        </button>
                        </td>
                    </tr>
                    </tbody>
                </table>

                <p class="center"><em>No items in cart</em></p>
                <div class="spread">
                    <span><strong>Total:</strong> $1.00</span>
                    <button class="btn btn-light">Checkout</button>
                </div>
                </div>
                </div>
            </v-row>
        </v-card>
    </v-col>
</template>