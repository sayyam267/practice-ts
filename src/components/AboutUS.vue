<template>
    <v-container>
      <div>
         <v-alert
      border="left"
      colored-border
      color="info "
      elevation="2"
    >
      Aliquam eu nunc. Fusce commodo aliquam arcu. In consectetuer turpis ut velit. Nulla facilisi..

      Morbi mollis tellus ac sapien. Fusce vel dui. Praesent ut ligula non mi varius sagittis. Vivamus consectetuer hendrerit lacus. Suspendisse enim turpis, dictum sed, iaculis a, condimentum nec, nisi.
    </v-alert>
      </div>
        <!-- <div>password <div> <input type="password" v-model="pass" placeholder="enter pass"> <div >{{helperText}}</div> </div> </div> -->
    </v-container>
</template>

<script lang="ts">


import{Vue,Component,Prop,Watch} from 'vue-property-decorator'

@Component
export default class AboutUs extends Vue {
    @Prop() private about!: string;
    pass='';
    helperText='';

    @Watch('pass')
    onPropertyChanged(val:string){
        if(val.length<8){
            this.helperText = "password must be at least 8 characters";
        }
        else if(val.length>32){
            this.helperText = "password cannot greater than 32 characters";
        }
        else{
            this.helperText = "";
        }
    }


}
</script>
