<template>
<div class="container">
<h1 style="text-align:center">DATA ENTRY</h1>
    <v-form> 
      <div id="box">
        <v-text-field
        v-model="shipping.dano"
        label="DA Number"
        required
      ></v-text-field>
      <v-text-field
        v-model="shipping.supplier"
        label="Supplier"
        required
      ></v-text-field>
      <v-text-field
        v-model="shipping.weight"
        label="Box Weight"
        required
      ></v-text-field>
      <v-text-field
        v-model="shipping.lengthh"
        label="Box Length"
        required
      ></v-text-field>  <v-text-field
        v-model="shipping.breadth"
        label="Box Breadth"
        required
      ></v-text-field>
      <v-text-field
        v-model="shipping.height"
        label="Box Height"
        required
      ></v-text-field>
    <v-select
      v-model="shipping.type"
      :items="items"
      label="Box Type"
      required
    ></v-select>
      <v-btn @click="submit()" style="float:right;">
        submit
      </v-btn>
      <v-btn style="float:right;">clear</v-btn>
      <v-btn style="float:left;">Home</v-btn>
      </div>
      
    </v-form>
    
 
 

</div>    
</template>

<script>
import axios from 'axios'
import request from 'axios'
 export default {
    data: () => ({
    //  select:['cardboard'],
     items:['cardboard','wooden box'],
     shipping:[
        {dano :'',supplier :'', weight:'', lengthh:'', breadth:'', height:'',type:''}
      ],
      err_msg:'no records'
      }),
      methods:{
        submit()
        {
          var self = this;
          var shipping_details = self.shipping
          this.$axios.post("http://localhost/api/insert.php",shipping_details).then(function(para){
          // var result =  para.data;  
          // if(result[0])
          // {
          //   self.values=result[1];
          //   console.log("connectedq")
          // }
          // else
          // {
    	    // 	ship.err_msg = result[1];
          // }
          console.log(para)
  });
  
  }   

 }
 }
</script>

<style>
.container{
  border : 2px solid #fff;
  margin-top: 5%;
  padding-top: 3%; 
}
#box{
  align-content: center;  
}
</style>
