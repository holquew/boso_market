<template>
  <v-app id="keep">
    <v-navigation-drawer
      v-model="drawer"
      class="grey lighten-4"
      app
      clipped
      absolute
      >
      <v-list
        dense
        class="grey lighten-4"
      >
        <template v-for="(item, i) in items">
          <v-layout
            v-if="item.heading"
            :key="i"
            row
            align-center
          >
            <v-flex xs6>
              <v-subheader v-if="item.heading">
                {{ item.heading }}
              </v-subheader>
            </v-flex>
            <v-flex xs6 class="text-xs-right">
              <v-btn small flat>edit</v-btn>
            </v-flex>
          </v-layout>
          <v-divider
            v-else-if="item.divider"
            :key="i"
            dark
            class="my-3"
          ></v-divider>
          <v-list-tile
            v-else
            :key="i"
            @click=""
          >
            <v-list-tile-action>
              <v-icon>{{ item.icon }}</v-icon>
            </v-list-tile-action>
            <v-list-tile-content>
              <v-list-tile-title class="grey--text">
                {{ item.text }}
              </v-list-tile-title>
            </v-list-tile-content>
          </v-list-tile>
        </template>
      </v-list>
    </v-navigation-drawer>
    <v-toolbar color="amber" app absolute clipped-left>
      <v-toolbar-side-icon @click="drawer = !drawer"></v-toolbar-side-icon>
      <span class="title ml-3 mr-5">VueShop&nbsp;</span>
      <v-spacer></v-spacer>
      <v-text-field
        solo-inverted
        flat
        hide-details
        label="Search"
        prepend-inner-icon="search"
      ></v-text-field>
      <v-spacer></v-spacer>
      <v-flex xs2>
        <span>
         <router-link
        to="/register"
        tag="v-btn"
        >
          <v-btn small flat>Register&nbsp;</v-btn>
        </router-link>
        </span>
        <span>
        <router-link
        to="/login"
        tag="v-btn"
        >
          <v-btn small flat>Login&nbsp;</v-btn>
        </router-link>

        </span>
      </v-flex>      
    </v-toolbar>
  <v-content>
    <v-container fluid fill-height class="grey lighten-4">
      <v-layout justify-center align-center>
        <nuxt />
      </v-layout>
    </v-container>
  </v-content>
  </v-app>
</template>

<script>
  export default {
    data: () => ({
      drawer: null,
      items: [
        { icon: 'label', text: 'Home', to: '/' },
        { icon: 'shopping_cart', text: 'Items', to: '/itemList' },
        { icon: 'add_shopping_cart', text: 'Sell', to: '/itemAdd' }
      ]
    }),
    props: {
      source: String
    }
  }
</script>

<style lang="stylus">
  #keep
    .v-navigation-drawer__border
      display: none
</style>
