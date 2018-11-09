<template>
<div class="container">
 <h1 id='header' style="text-align:center">BOX SELECTION</h1>
  <v-data-table
    v-model="selected"
    :headers="headers"
    :items="values"
    :pagination.sync="pagination"
    select-all
    item-key="name"
    class="elevation-1"
  >
    
    <template slot="headers" slot-scope="props">
      <tr>
        <th></th>
        <th
          v-for="header in props.headers"
          :key="header.text"
          :class="['column sortable', pagination.descending ? 'desc' : 'asc', header.value === pagination.sortBy ? 'active' : '']"
          @click="changeSort(header.value)"
        >
          <v-icon small>arrow_upward</v-icon>
          {{ header.text }}
        </th>
      </tr>
    </template>
     <template slot="items" slot-scope="props">
      <tr :active="props.selected">
        <td>
          <input type="checkbox" v-bind:value="props.item" v-model="selected">
        </td>
      <td class="text-xs-center">{{ props.item.dano }}</td>
      <td class="text-xs-center">{{ props.item.supplier}}</td>
      <td class="text-xs-center">{{ props.item.weight }}</td>
      <td class="text-xs-center">{{ props.item.length }}</td>
      <td class="text-xs-center">{{ props.item.breadth }}</td>
      <td class="text-xs-center">{{ props.item.height }}</td>
      </tr>
    </template>
  </v-data-table>
      <v-btn v-bind:disabled = 'btn_switch()' @click="selected = values" style="float:right;">Select All</v-btn>
      <v-btn v-bind:disabled = 'btn_switch2()' @click="selected=[]" style="float:right;">Clear All</v-btn>
      <v-btn @click="home()" slot="activator" style="float:left;">Home</v-btn>
      <v-layout row justify-center>
    <v-dialog v-model="dialog" persistent max-width="500px">
      <v-btn slot="activator">SUBMIT</v-btn>
      <v-card>
        <v-card-title>
          <span class="headline">Shipping Details</span>
        </v-card-title>
        <v-card-text>
          <v-container grid-list-md>
            <v-layout wrap>
              <v-flex xs12 sm12>
                <v-select
                  :items="['SPP', 'vehicle']"
                  label="Mode of Dispatch"
                  required hint="Choose mode of transfer"
                  v-model="shipping.transport"
                ></v-select>
              </v-flex>
              <v-flex xs12 sm12>
                <v-text-field v-model="shipping.vehicle" label="Vehicle" required hint="Enter the vehicle"></v-text-field>
              </v-flex>
              <v-flex xs12 sm12>
                <v-text-field v-model="shipping.lrno" label="LR Number" required hint="Enter the LR number"></v-text-field>
              </v-flex>
            </v-layout>
             </v-container>
          <small>*indicates required field</small>
        </v-card-text>
        <v-card-actions>
          <v-spacer></v-spacer>
          <v-btn color="blue darken-1" flat @click.native="dialog = false" >Close</v-btn>
           <v-btn color="blue darken-1" flat @click.native="dialog = true" @click="cleardialog()">Clear</v-btn>
          <v-btn color="blue darken-1" @click.native="dialog = true" flat @click="save(shipping)">Save</v-btn>
        </v-card-actions>
      </v-card>
    </v-dialog>
  </v-layout>
  
</div>
</template>
<script>
  export default {
    data(){
        return{
            pagination: {
        sortBy: 'name'
      },
      dialog:false,
      selected: [],
      shipping:[
        {
          vehicle:'',
          lrno:'',
          transport:''
        }
      ],
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
            dano:'1',
            supplier: '2',
            weight:'3',
            length:'4',
            breadth:'5',
            height:'6'
          },
          {
            dano:'6',
            supplier: '5',
            weight:'4',
            length:'3',
            breadth:'2',
            height:'1'
          },
          {
            dano:'3',
            supplier: '5',
            weight:'4',
            length:'3',
            breadth:'2',
            height:'1'
          }
        ]
    }
},

    methods: {
      changeSort (column) {
        if (this.pagination.sortBy === column) {
          this.pagination.descending = !this.pagination.descending
        } else {
          this.pagination.sortBy = column
          this.pagination.descending = false
        }
      }, 
  send()
  {
  //
  },
  btn_switch(){
    if(this.selected.length === this.values.length)
    return true
    else return false
  },
  btn_switch2(){
    if(this.selected.length == 0)
    return true
    else return false
  },
 home()
  {
    this.$router.push("/");
  },
  save(shipping)
  {
    console.log(this.shipping)
  },
  cleardialog()
  {

  }
}
}
</script>
<style>
.v-datatable__actions{
    display:none;
}
.container{
    margin-top:5%;
}
#header{
    margin-bottom: 2%;
}
.dialog-btn{
  float:right
}
</style>
