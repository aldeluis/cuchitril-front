<template>
  <div>
    <v-card
      class="d-flex align-content-center flex-wrap justify-space-between"
      color="grey lighten-2"
      flat
      tile
    >
      <v-card v-for="n in 30" :key="n" class="pa-2" tile>
        Producto
      </v-card>
    </v-card>
  </div>
</template>
