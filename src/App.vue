<template>
  <v-app>
    <v-app-bar
      app
      color="white"
      dark
      height="45"
    >
    <div class="container d-flex align-center">
      <div class="d-flex align-center">
        <!-- <v-img
          alt="Vuetify Logo"
          class="shrink mr-2"
          contain
          src="https://cdn.vuetifyjs.com/images/logos/vuetify-logo-dark.png"
          transition="scale-transition"
          width="40"
        /> -->

        <!-- <v-img
          alt="Vuetify Name"
          class="shrink mt-1 hidden-sm-and-down"
          contain
          min-width="100"
          src="https://cdn.vuetifyjs.com/images/logos/vuetify-name-dark.png"
          width="100"
        /> -->
        <div class="text-caption black--text">A MIDWEST HIP-HOP COLLECTIVE - Beta v 2.0</div>
      </div>

      <v-spacer></v-spacer>

      <v-btn
        href="https://github.com/vuetifyjs/vuetify/releases/latest"
        target="_blank"
        small
        :ripple="false"
        icon
        v-for="(data,i) in socialLinks"
        :key="i"
      >
        <v-icon class="black ">{{data.icon}}</v-icon>
      </v-btn>
      </div>
    </v-app-bar>
     
    <v-main class="black darken-2">
       <div class="d-flex justify-center  mt-5"><v-img
          alt="Vuetify Logo"
          class="shrink mr-2"
          contain
          src="http://www.doomtree.net/wp-content/uploads/2016/01/dtr_logo_nokings_TEMP.png"
          transition="scale-transition"
          width="100"
        />
      </div>
      <div class="container text-center mt-5">
        <v-btn plain text color="white" to="/">HOME</v-btn>
        <v-btn plain text color="white" to="/about">ABOUT </v-btn>
        <v-btn plain text color="white" to="/shows">SHOWS</v-btn>
        <v-btn plain text color="white" to="/listen">LISTEN</v-btn>
        <v-btn plain text color="white" to="/watch">WATCH</v-btn>
        <v-btn plain text color="white" to="/release">RELEASE</v-btn>
        <v-btn plain text color="white" to="/news">NEWS</v-btn>
        <v-btn plain text color="white" to="/store">STORE</v-btn>
        <v-btn plain text @click="search" color="white"><v-icon class="black darken-2">mdi-magnify</v-icon></v-btn>
       <div>
       <v-fade-transition>
          <v-overlay
            v-if="isSearch"
            color="#fff"
            @click="isSearch = !isSearch"
            opacity="0.9"
          >
         
          <h2 class="black--text">TYPE AND PRESS ENTER TO SEARCH</h2>
           
          <input type="text" autofocus class="text-field-transparent" />
          </v-overlay>
        </v-fade-transition>
      </div>

      </div>
      <router-view/>
    </v-main>
  </v-app>
</template>

<script lang="ts">
import Vue from 'vue';

export default Vue.extend({
  name: 'App',

  data: () => ({
    isSearch:false,
    socialLinks:[
      {
        icon:'mdi-facebook'
      },
      {
        icon:'mdi-twitter'
      },
      {
        icon:'mdi-github'
      },
      {
        icon:'mdi-soundcloud'
      }
    ]
  }),
  methods:{
    search(){
      this.isSearch = true;
    }
  }
});
</script>

<style scoped>
.v-btn--active{
  border-bottom: 2px solid white;
}
.v-btn{
  border-radius: 0px;
}
.text-field-transparent{
  background: transparent !important;
  border: none !important;
  font-size:5em;
  text-align: center;
}
.snake{
  height: 100vh;
}
input:focus{
  outline: none !important;
  border: none !important;
}
</style>
