<template>
  <v-container fluid>
    <v-row>
      <v-col
        v-for="n in 30"
        :key="n"
        :cols="colnum"
      >
        <v-card flat>
          <v-img
            :src="`https://picsum.photos/500/300?image=${n * 5 + 10}`"
            :lazy-src="`https://picsum.photos/10/6?image=${n * 5 + 10}`"
            aspect-ratio="1.2"
            class="grey lighten-2"
          >
            <v-card-actions>
              <v-btn small rounded absolute top depressed right class="title white--text" color="red lighten-2" >25 €</v-btn>
              <v-btn :elevation=6 rounded small absolute right bottom color="red lighten-2 white--text">+<v-icon>mdi-cart</v-icon></v-btn>
            </v-card-actions>
            <!--<v-card-text >{{n}} {{colnum}}</v-card-text>-->
          </v-img>
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>
<script>
  export default {
    computed: {
      colnum () {
        const { xl, lg, md, sm, xs } = this.$vuetify.breakpoint
        return xl? 2 : lg? 3 : md? 3 : sm? 4 : xs? 6 : 12
      },
    },
  }
</script>
