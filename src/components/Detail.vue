<template>
  <v-container class="pa-10">
        <v-row>
            <v-col cols="12" md="12">
              <h2 class="white--text">{{detail.Title}} (17+)</h2>
            </v-col>
            <v-col cols="12" md="4">
              <v-img :src="detail.Poster" class="rounded-xl"></v-img>
            </v-col>
            <v-col cols="12" md="8">
                <h4 class="white--text font-weight-regular">Release Date : {{ $moment(detail.Released).format('DD-MM-YYYY') }}</h4>
                <h4 class="white--text font-weight-regular">Language: {{detail.Language}}</h4>
                <h4 class="white--text font-weight-regular">Genre: {{detail.Genre}}</h4>
                <h4 class="white--text font-weight-regular">Cast & Crew: {{detail.Actors}}</h4>
                <h4 class="white--text font-weight-regular">Director: {{detail.Director}}</h4>
                <h4 class="white--text font-weight-regular">Length: {{detail.Runtime}}</h4>
                <h2 class="white--text py-4">SINOPSIS</h2>
                <h4 class="white--text font-weight-regular">{{detail.Language}}</h4>
                <p class="white--text">{{detail.Plot}}</p>
                <div>
                  <v-btn large color="#C0222E" class=" font-weight-bold white--text mr-3 rounded-lg my-2"> Buy Ticket</v-btn>
                  <v-btn large color="#C0222E" class=" font-weight-bold white--text rounded-lg my-2"> Watch Trailer</v-btn>
                </div>
            </v-col>

            <v-col cols="12" md="12" class="my-2">
              <h2 class="white--text font-weight-regular">Now Playing</h2>
            </v-col>
            <v-col cols="12" md="4" v-for="i in 3" :key="i">
               <v-img :src="detail.Poster" class="rounded-xl"></v-img>
            </v-col>
        </v-row>
    </v-container>
</template>

<script>

import axios from 'axios'

export default {
    name: 'DetailComponents',
    data(){
        return {
            detail:{}
        }
    },
    mounted(){
        
        const id = this.$route.params.id
        const url = "http://www.omdbapi.com/"
        const apiKey = "271ab1b1"

        axios.get(url,{
        params:{
          apiKey:apiKey,
          i: id
        }
      }).then(res =>{
        this.detail =  res.data
      })
    }
}
</script>

<style>

</style>