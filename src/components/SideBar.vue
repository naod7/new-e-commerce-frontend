<template>
    <nav>
          <v-navigation-drawer   app  dark color="#3853D8" width="100">
          <div class="text-center mt-5">
            <router-link to="/"> <v-btn fab color="white" x-large>
                 <v-icon color="black">mdi-home-outline</v-icon>
             </v-btn></router-link>
          </div>
          <v-divider horizontal class="ml-3 mr-3"></v-divider>
          <div class="text-center mt-5" style="position: bottom: 2px;">
            <router-link to="/products"><v-btn fab color="white" x-large>
                <v-icon color="black">mdi-truck-outline</v-icon>
            </v-btn>
            </router-link>
          </div>
          <v-divider horizontal class="ml-3 mr-3"></v-divider>
          <div class="text-center mt-5">
            <v-btn fab color="white" x-large>
                <v-icon color="black">mdi-heart-outline</v-icon>
            </v-btn>
          </div>
          <v-divider horizontal class="ml-3 mr-3"></v-divider>
          <div class="text-center mt-5">
            <v-btn fab color="white" x-large>
                <v-badge color="#94D0EF" content="2">
                    <v-icon>mdi-cart-outline</v-icon>
                </v-badge>
            </v-btn>
          </div>

          <div style="position: absolute; bottom: 20px;
          margin-left: auto; margin-right: auto; left:0; right: 0; text-align: center;">
                  <v-btn text>
                      <v-icon>fas fa-sign-out-alt</v-icon>
                  </v-btn>



          </div>
          </v-navigation-drawer>
      </nav>
  </template>

  <script>
  export default {
   data: () => ({
          selectedItem: 0,
          drawer: null,
          items: [
              {icon: 'fas fa-home', text: 'Discover'},
              {icon: 'fas fa-th-large', text: 'Stream'},
              {icon: 'fas fa-calendar', text: 'Community'},
              {icon: 'fas fa-archive', text: 'Statistics'},
              {icon: 'fas fa-cog', text: 'Statistics'},
          ],
   })
  }
  </script>

  <style scoped>





  .border  {

      background: #fff ;
      border-top-left-radius: 30px;
      border-bottom-left-radius: 30px;
        text-decoration: none;

  }

  .border b:nth-child(1)
  {

      position: absolute;
      top: -20px;
      height: 20px;
      width: 83%;
      background: #fff;

      display: none;
  }
  .border b:nth-child(1)::before
  {
      content: '';
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      border-bottom-right-radius: 20px;
      background: black;
  }

  .border b:nth-child(2)
  {
      position: absolute;
      bottom: -20px;
      height: 20px;
      width: 83%;
      background: #fff;
      display: none;
  }
  .border b:nth-child(2)::before
  {
      content: '';
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      border-top-right-radius: 20px;
      background: black;
  }
  .border b:nth-child(1),
  .border b:nth-child(2)
  {
      display: block;
  }

  </style>