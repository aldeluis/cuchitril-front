<template>
  <v-app>
    <v-navigation-drawer
      v-model="drawer"
      :mini-variant="miniVariant"
      :clipped="clipped"
      fixed
      app
    >
      <v-list>
        <v-list-item
          v-for="(item, i) in menuizquierdo"
          :key="i"
          :to="item.to"
          router
          exact
        >
          <v-list-item-action>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title v-text="item.title" />
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <v-app-bar :clipped-left="clipped" fixed app>
      <v-app-bar-nav-icon @click.stop="drawer = !drawer" />
      <v-spacer />
      <v-toolbar-title v-text="title" class="saira-stencil-one grande" />
      <v-spacer />
      <v-btn @click.stop="rightDrawer = !rightDrawer" icon>
        <v-icon>mdi-cart</v-icon>
      </v-btn>
    </v-app-bar>
    <v-content>
      <v-container>
        <nuxt />
      </v-container>
    </v-content>
    <v-navigation-drawer v-model="rightDrawer" :right="right" temporary fixed>
      <v-list>
        <!-- <v-list-item @click.native="right = !right">
          <v-list-item-action>
            <v-icon light>
              mdi-repeat
            </v-icon>
          </v-list-item-action>
          <v-list-item-title>Switch drawer (click me)</v-list-item-title> -->
        <!-- </v-list-item> -->
      </v-list>
    </v-navigation-drawer>
    <v-footer :fixed="fixed" app>
      <span>&copy; el cuchitril 2020</span>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  data() {
    return {
      clipped: false,
      drawer: false,
      fixed: false,
      menuizquierdo: [
        {
          icon: 'mdi-hand-left',
          title: 'Bienvenida',
          to: '/'
        },
        {
          icon: 'mdi-tshirt-crew',
          title: 'Camisetas',
          to: '/camisetas'
        },
        {
          icon: 'mdi-brush',
          title: 'Arte',
          to: '/arte'
        }
      ],
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: 'el cuchitril'
    }
  }
}
</script>

<style scoped>
.saira-stencil-one {
  font-family: 'Saira Stencil One', 'Arial', sans-serif;
}

.grande {
  font-size: 22pt;
}
</style>
