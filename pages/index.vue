<template>
   <div>
 <div class="jumbotron"  style="border: 3px solid black; margin:20px">
 <h3 style="margin-left:9%" class="display-3"><i style="margin-right:50px; align-content:center"  class="fa fa-truck"></i >Product Shipping</h3>
</div>
   
    <div class="text-xs-center">
	<v-layout>
      <v-flex xs12 sm6 style="margin-left:20px">
        <v-card>
           <v-card-media src="https://images.unsplash.com/photo-1507208773393-40d9fc670acf?ixlib=rb-0.3.5&ixid=eyJhcHBfaWQiOjEyMDd9&s=b6768885e6bbb2cef343010ce679b6d0&auto=format&fit=crop&w=500&q=60" height="200px">
          </v-card-media>
          <v-card-title primary-title>
            <div>
<v-btn flat color="orange" class="button" outline @click="entry()">Data Entry</v-btn>
              </div>
          </v-card-title>
        </v-card>
      </v-flex>
       <v-flex xs12 sm6 style="margin-left:20px">
        <v-card>
          <v-card-media src="https://images.unsplash.com/photo-1520406625550-148d283f3620?ixlib=rb-0.3.5&ixid=eyJhcHBfaWQiOjEyMDd9&s=6aa2e7dc874f1ffb138c52c47adf72c2&auto=format&fit=crop&w=500&q=60" height="200px">
          </v-card-media>
          <v-card-title primary-title>
            <div>
<v-btn flat color="orange" outline @click="display()">Data Display</v-btn>            </div>
          </v-card-title>
        </v-card>
      </v-flex>
       <v-flex xs12 sm6 style="margin-left:20px">
        <v-card>
          <v-card-media src="https://images.unsplash.com/photo-1470173274384-c4e8e2f9ea4c?ixlib=rb-0.3.5&ixid=eyJhcHBfaWQiOjEyMDd9&s=8f8bf185da8d21fad65f2636d6021ba7&auto=format&fit=crop&w=500&q=60" height="200px">
          </v-card-media>
          <v-card-title primary-title>
            <div>
<v-btn flat color="orange" outline @click="box()">Packing</v-btn>
            </div>
          </v-card-title>
        </v-card>
      </v-flex>
       <v-flex xs12 sm6 style="margin-left:20px; margin-right:20px">
        <v-card>
          <v-card-media src="https://images.unsplash.com/photo-1446694292248-2c2a7e575b1b?ixlib=rb-0.3.5&ixid=eyJhcHBfaWQiOjEyMDd9&s=b6ac3f086fb54a1290c3cdb741d5a2cb&auto=format&fit=crop&w=500&q=60" height="200px">
          </v-card-media>
          <v-card-title primary-title>
            <div>
            <v-btn flat color="orange" outline @click="pack()">Shipping</v-btn>
            </div>
          </v-card-title>
        </v-card>
      </v-flex>
    </v-layout>   
  </div>
  </div>
</template>


<script>
export default {
methods:
{
  entry()
  {
  this.$router.push("/data_entry");
  },
  display()
  {
    this.$router.push("/data_display");
  },
  box(){
this.$router.push("/selection");
  },
  pack(){
this.$router.push("/packing");
  }
}
}
</script>

<style>
.jumbotron
{
/* backgound: url("https://images.unsplash.com/photo-1518978054039-e4682dbc9a5d?ixlib=rb-0.3.5&ixid=eyJhcHBfaWQiOjEyMDd9&s=0fb711da47a6fb7cb511ce28b281a27f&auto=format&fit=crop&w=500&q=60"); */
background: #FFB75E;  /* fallback for old browsers */
background: -webkit-linear-gradient(to right, #ED8F03, #FFB75E);  /* Chrome 10-25, Safari 5.1-6 */
background: linear-gradient(to right, #ED8F03, #FFB75E); /* W3C, IE 10+/ Edge, Firefox 16+, Chrome 26+, Opera 12+, Safari 7+ */
background-size: cover;
color:#000000;
/* text-shadow: 4px 2px #ffffff; */
font-family:  serif;
font-size:20px
}
</style>