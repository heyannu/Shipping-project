<template>
  <div class="container">
    <v-layout row>
      <v-flex xs4>
        <v-subheader  style="margin-left:150px">Mode of Dispatch:</v-subheader>
      </v-flex>
      <v-flex xs8  style="margin-top: 10px; margin-left:130px">
        vehicle
      </v-flex>
    </v-layout>
     <v-layout row>
      <v-flex xs4>
        <v-subheader  style="margin-left:150px">Vehicle:</v-subheader>
      </v-flex>
      <v-flex xs8  style="margin-top: 10px; margin-left:130px">
       Truck
      </v-flex>
    </v-layout>
     <v-layout row>
      <v-flex xs4>
         <v-subheader  style="margin-left:150px">LR Number:</v-subheader>
      </v-flex>
      <v-flex xs8  style="margin-top: 10px; margin-left:130px">
       AW4567af
      </v-flex>
    </v-layout>
     <v-layout row>
      <v-flex xs4>
          <v-subheader  style="margin-left:150px">Box:</v-subheader>
      </v-flex>
      <v-flex xs8  style="margin-top: 10px; margin-left:130px">
        box136
        
      </v-flex>
    <ul v-for="items in shipping" :key=items>
      <li>{{items.dano}}</li>
      <li>{{items.supplier}}</li>
      <li>{{items.weigth}}</li>
      <li>{{items.length}}</li>
      <li>{{items.breadth}}</li>
      <li>{{items.height}}</li>
    </ul>
    </v-layout>
       <div class="text-xs-center">
    <v-btn outline color="indigo" @click="home()">Home</v-btn>
    </div>
    </div>
</template>
<script>
import axios from 'axios'
import request from 'axios'
export default {
    data()
    {
     return{
            ship:{
                mode:'',
                vehicle:'',
                lrno:'',
            },
            shipping:[],
            err_msg:'no record',

        }
    },
    
created()
{
  this.retrieve();
},
methods:
{  
  retrieve()
  { 
    var self = this;
  this.$axios.get("http://localhost/api/retrieve.php").then(function(para){
  var result =  para.data;  
        // if(result[0])
        // {
        //   self.shipping=result[1];
        //   console.log(self.shipping)
        // }
        // else
        // {
    	  // 	ship.err_msg = result[1];
        // }
  });
  
  }   
}
}
</script>
