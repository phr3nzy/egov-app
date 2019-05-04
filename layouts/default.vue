<template>
  <v-app light>
    <v-navigation-drawer
      v-model="drawer"
      :mini-variant="false"
      :clipped="true"
      floating
      flat
      fixed
      app
    >
      <v-list>
        <v-list-tile
          v-for="(item, i) in items"
          :key="i"
          active-class="secondary--text"
          :to="item.to"
          router
          exact
        >
          <v-list-tile-action>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-tile-action>
          <v-list-tile-content>
            <v-list-tile-title v-text="item.title" />
          </v-list-tile-content>
        </v-list-tile>
      </v-list>
    </v-navigation-drawer>
    <v-toolbar :clipped-left="true" fixed flat app>
      <v-toolbar-side-icon flat color="secondary" @click="drawer = !drawer" />
      <!-- <v-toolbar-title v-text="title" /> -->
      <v-spacer />
    </v-toolbar>
    <v-content>
      <v-container>
        <nuxt />
      </v-container>
    </v-content>
    <!-- <v-footer color="transparent" :clipped="false" :fixed="fixed" app>
      <v-flex xs12 text-xs-center>
        &copy; E-Sud | All Rights Reserved
      </v-flex>
    </v-footer> -->
  </v-app>
</template>

<script>
export default {
  data() {
    return {
      drawer: false,
      fixed: true,
      items: [
        {
          icon: 'home',
          title: 'Home',
          to: '/'
        },
        {
          icon: 'person',
          title: 'Sign in',
          to: '/signin'
        }
      ],
      title: 'E-Sud for Citizen Identity and Services'
    }
  }
}
</script>
