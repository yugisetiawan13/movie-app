<template>
    <div>
      <v-app-bar flat app color="#C0222E">
        <v-app-bar-nav-icon class="hidden-md-and-up white--text" @click="drawer = !drawer"></v-app-bar-nav-icon>
          <v-text-field
            label="Search Title / Theatre Here"
            dense
            solo
            class="mt-5 rounded-lg"
          ></v-text-field>
          <v-spacer></v-spacer>
          <div class="d-flex mr-2">
              <v-img class="shrink mr-2 hidden-sm-and-down"  alt="Movie-App" contain width="100" min-width="100" src="../assets/imax.png"></v-img>
              <v-img class="shrink  hidden-sm-and-down"  alt="Movie-App" contain width="100" min-width="100" src="../assets/dolby.png"></v-img>
          </div>
      </v-app-bar>

      <v-navigation-drawer app v-model="drawer" color="#191C1F" mini-variant mini-variant-width="250">
        <v-list-item style="background-color:#C0222E">
          <v-list-item-content>
            <v-list-item-title class="py-1" >
              <v-img class="shrink"  alt="Movie-App" contain width="100" min-width="100" src="../assets/merdeka.png"></v-img>
            </v-list-item-title>
          </v-list-item-content>
        </v-list-item>
        <v-list>
          <v-list-item class="mb-2" v-for="(item , i ) in items" :key="i" link :to="item.route">
            <v-list-item-content>
              <v-list-item-title class="white--text" v-text="item.title"></v-list-item-title>
            </v-list-item-content>
          </v-list-item >
        </v-list>
      </v-navigation-drawer>
    </div>
</template>

<script>
export default {
  name:"ToolBar",
  data(){
    return {
      drawer : true,
      items:[
        {title:"Now Playing" , route:"/"},
        {title:"Coming Soon"},
        {title: "Theatre"},
        {title:"Promotion"},
        {title:"Information"},
      ],
    }
  },
}
</script>

<style scoped>
  

</style>