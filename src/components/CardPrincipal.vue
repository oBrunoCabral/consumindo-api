<template>
  <div>
    <v-row class="d-none d-sm-flex">
      <v-card
        class="mx-auto"
        :width="width"
      >
        <v-img
          class="white--text"
          height="200px"
          src="../assets/images/cover.jpg"
        >
          <v-card-title class="align-end fill-height" id="titulo-card">Card Title</v-card-title>
        </v-img>
        
        <v-card-text id="texto-card">{{quote}} <br>- {{author}}</v-card-text>
        <v-card-actions>
          <v-btn
            text
            color="orange"
            v-on:click="novoQuote()"
          >
            Click
          </v-btn>
        </v-card-actions>
      </v-card>
    </v-row>
    <v-row class="d-flex d-sm-none">
      <v-col>
        <v-card
          class="mx-auto"
          :tile="tile"
          :elevation="elevation"
        >
          <v-img
            class="white--text"
            height="50vh"
            src="../assets/images/cover.jpg"
          >
            <!-- <v-card-title class="align-end fill-height" id="titulo-card"></v-card-title> -->
          </v-img>
          
          <v-card-text id="texto-card">
            {{quote}}<br>
            - {{author}}
          </v-card-text>
        </v-card>
        <v-row style="margin-top: 5vh;" align="center" justify="center">
          <v-btn
            class="ma-2"
            dark
            color="#263238"
            bottom="false"
            v-on:click="novoQuote()"
          >
            Gerar Nova Frase
          </v-btn>
        </v-row>
      </v-col>
    </v-row>

  </div>
</template>

<script>
  import axios from "axios";

  export default {
    data(){
      return {
        width: 500,
        tile: true,
        elevation: 5,
        errors:[],
        quote: '',
        author: ''

      }
    },
    methods: {
      novoQuote: function(event){
        axios.get('https://breaking-bad-quotes.herokuapp.com/v1/quotes')
          .then(response => {
          this.posts = response.data
          var result = this.posts[0].quote
          this.quote = response.data[0].quote
          this.author = response.data[0].author
          //console.log(response.data[0].quote)
          //console.log(result)
        })
      },
    },
    created(){
      axios.get('https://breaking-bad-quotes.herokuapp.com/v1/quotes')
      .then(response => {
        this.posts = response.data
        var result = this.posts[0].quote
        this.quote = response.data[0].quote
        this.author = response.data[0].author
        //console.log(response.data[0].quote)
      })
      .catch(e => {
        this.errors.push(e)
        console.log(this.errors.push(e))
      })
    },
  }
</script>