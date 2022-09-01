<template>
  <v-container>
   
    <div class="d-flex mb-3">
    <v-hover v-for="(data,i) in images" :key="i">
      
    <template v-slot:default="{ hover }" >
      
       <v-img
          :src="data.img"
          class="my-3"
          :width="width"
          :height="height">
          
       
       <v-fade-transition>
          <v-overlay
            v-if="hover"
            absolute
            color="#000"
          >
            <v-img
          :src="'http://www.doomtree.net/wp-content/uploads/2016/04/logo_papertiger_200x300.png'"
          class="my-3"
          :width="width"
          :height="height"/>
          </v-overlay>
        </v-fade-transition>
      </v-img>
        
    </template>
  
  </v-hover>

  <!-- img section end -->

    </div>
   
    <v-carousel hide-delimiter-background	
      v-model="model"
      continuous
      height="400"
      cycle
      class="mb-5">
    <v-carousel-item
      v-for="(color, i) in colors"
      :key="color"
    >
    
      <!-- <v-sheet
        :color="color"
        height="100%"
        tile
      >
        <v-row
          class="fill-height"
          align="center"
          justify="center"
        >
          <div class="text-h2">
            Slide {{ i + 1 }}
          </div>
        </v-row>
      </v-sheet> -->
       <v-img
          :src="'https://www.doomtree.net/wp-content/uploads/dtrpatreon.jpg'"
          class="my-3"
          contain
          height="100%"
          :key="i"
        />
    </v-carousel-item>
  </v-carousel>

   <v-row class="text-center">
      <v-col cols="6">
       <v-row >
         <v-col cols="5" dark class="px-4"><v-progress-linear color="white" class="mt-4" value="100"></v-progress-linear></v-col>
         <v-col cols="2" ><h2 class="white--text">NEWS</h2></v-col>
         <v-col cols="5" class="px-4"><v-progress-linear class="mt-4" color="white" value="100"></v-progress-linear></v-col>
       </v-row>
       <div class="white--text"> </div>
      </v-col>

     <v-col cols="6">
       <v-row >
         <v-col cols="4" dark ><v-progress-linear color="white" class="mt-4" value="100"></v-progress-linear></v-col>
         <v-col cols="4" ><h2 class="white--text">LISTEN UP</h2></v-col>
         <v-col cols="4" ><v-progress-linear class="mt-4" color="white" value="100"></v-progress-linear></v-col>
       </v-row>

       <div class="white--text">
        <iframe width="100%" height="300" scrolling="no" frameborder="no"  src="https://w.soundcloud.com/player/?url=https%3A//api.soundcloud.com/tracks/1335776533&color=%23ff5500&auto_play=true&hide_related=false&show_comments=true&show_user=true&show_reposts=false&show_teaser=true&visual=true"></iframe><div style="font-size: 10px; color: #cccccc;line-break: anywhere;word-break: normal;overflow: hidden;white-space: nowrap;text-overflow: ellipsis; font-family: Interstate,Lucida Grande,Lucida Sans Unicode,Lucida Sans,Garuda,Verdana,Tahoma,sans-serif;font-weight: 100;"><a href="https://soundcloud.com/sayyam-ali-28620854" title="Sayyam Ali" target="_blank" style="color: #cccccc; text-decoration: none;">Sayyam Ali</a> · <a href="https://soundcloud.com/sayyam-ali-28620854/first-track" title="First Track" target="_blank" style="color: #cccccc; text-decoration: none;">First Track</a></div>
       </div>
      </v-col>
    </v-row>
  </v-container>
</template>

<script  lang="ts">
  import Vue from 'vue'

  export default Vue.extend({
    name: 'HelloWorld',

    data: () => ({
      width:130,
      height:230,
      model:0,
      colors: [
        'primary',
        'secondary',
        'yellow darken-2',
        'red',
        'orange',
      ],
      
      images: [
        {
          overlayImg: 'Explore components',
          img: 'http://www.doomtree.net/wp-content/uploads/widget_papertiger200x300.jpg',
        },
        {
          overlayImg: 'Explore components',
          img: 'http://www.doomtree.net/wp-content/uploads/widget_papertiger200x300.jpg',
        },
        {
          overlayImg: 'Explore components',
          img: 'http://www.doomtree.net/wp-content/uploads/widget_cecilotter200x300.jpg',
        },
        {
          overlayImg: 'Explore components',
          img: 'http://www.doomtree.net/wp-content/uploads/widget_lazerbeak200x300.jpg',
        },
        {
          overlayImg: 'Explore components',
          img: 'http://www.doomtree.net/wp-content/uploads/widget_mikemictlan200x300.jpg',
        },
        {
          overlayImg: 'Explore components',
          img: 'http://www.doomtree.net/wp-content/uploads/widget_sims200x300.jpg',
        },
        {
          overlayImg: 'Explore components',
          img: 'http://www.doomtree.net/wp-content/uploads/widget_pos200x300.jpg',
        },
      ],
    }),
  })
</script>
