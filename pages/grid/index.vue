<template>
<div>
   <v-card class='container' style="max-width:900px">
      <div grid-list-md>
        <v-layout row v-for="values in values" style="border:2px solid gray">        
         <v-flex xs12>
        <v-card color="blue-grey darken-2" class="white--text">
        <ul>
        <li>DA Number:  {{values.dano}}</li>
        <li>Supplier:  {{values.supplier}}</li>
        <li>Weight:  {{values.weight}}</li>
        <li>Length:  {{values.length}}</li>
        <li>Breadth:  {{values.breadth}}</li>
        <li>Height:  {{values.height}}</li>
        </ul>
        </v-card>
        </v-flex>
        </v-layout>
      </div>
    </v-card>
</div>
</template>
<script>
export default {
    data(){
        return{
            values:[
            {dano:'1',
            supplier: 'abc',
            weight:'50',
            length:'60',
            breadth:'34',
            height:'545'},
             
            {dano:'2',
            supplier: 'def',
            weight:'60',
            length:'70',
            breadth:'44',
            height:'845'},
            {dano:'1',
            supplier: 'abc',
            weight:'50',
            length:'60',
            breadth:'34',
            height:'545'}
           
            ]
        }
    }
}
</script>
<style>
.container{
    margin-top: 30px;
}
</style>
'