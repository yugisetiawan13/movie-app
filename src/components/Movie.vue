<template>

    <v-container class="pa-10">
      <v-row >
        <v-col cols="12" md="4" v-for="(item , i ) in films.slice(i,9)" :key="i" >
            <v-card link :to="{name: 'detail' , params: {id:item.imdbID} }" class="rounded-xl" >
                <v-img :src="item.Poster" min-height="300" max-height="450"></v-img>
            </v-card>
            <div class="white--text text-center mt-2">
              <h4 class="text-truncate">{{item.Title}}</h4>
              <span>(17+)</span>
            </div>
        </v-col>
      </v-row>
      <div class="text-center mt-10">
        <v-pagination
          v-model="page"
          :length="5"
          circle
          color="#C0222E"
          ></v-pagination>
      </div>
    </v-container>

</template>

<script>

  import axios from 'axios';

  export default {
    name: 'MovieComponents',
    data: () => ({
      films:[],
      page:1
    }),

    mounted(){

      const url = "http://www.omdbapi.com/"
      const apiKey = "271ab1b1"
      
      axios.get(url,{
        params:{
          apiKey:apiKey,
          s:'Demon Slayer'
        }
      }).then(res =>{
        this.films = res.data.Search
      })
    }


  }
</script>
