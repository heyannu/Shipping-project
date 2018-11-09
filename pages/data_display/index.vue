<template>
<div class="container">
    <h1 id='header' style="text-align:center">DATA DISPLAY </h1>
<v-data-table
    :headers="headers"
    :items="values"
    hide-actions
    class="elevation-1"
  >
    <template slot="items" slot-scope="props">
      <td class="text-xs-left">{{ props.item.dano }}</td>
      <td class="text-xs-left">{{ props.item.supplier}}</td>
      <td class="text-xs-left">{{ props.item.weight }}</td>
      <td class="text-xs-left">{{ props.item.length }}</td>
      <td class="text-xs-left">{{ props.item.breadth }}</td>
      <td class="text-xs-left">{{ props.item.height }}</td>
    </template>
  </v-data-table>
   <v-btn style="float:right;">
      HOME
      </v-btn>
</div>
</template>

<script>
import axios from 'axios'
import request from 'axios'
  export default {
    data () {
      return {
        headers: [
          { text: 'DA Number',value: 'dano'},
          { text: 'Supplier', value: 'supplier' },
          { text: 'Weight', value: 'weight' },
          { text: 'Length', value: 'length' },
          { text: 'Breadth', value: 'breadth' },
          { text: 'Height', value: 'height' }
        ],
        values: [
          {
            dano:'something',
            supplier: 'to',
            weight:'display',
            length:'in',
            breadth:'the',
            height:'table'
          }
        ],err_msg : "no records"
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
        if(result[0])
        {
          self.values=result[1];
        }
        else
        {
    	  	ship.err_msg = result[1];
        }
  });
  
  }   
}

  }
</script>
<style>
.container{
    margin-top:5%;
}
#header{
    margin-bottom: 2%;
}
</style>
