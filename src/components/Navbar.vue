<template>
  <nav>
    <v-navigation-drawer
      disable-resize-watcher="true" 
      v-model="drawer"
      app
      dark
      color="black"
    >
    <v-container>
      <v-row class="py-2">
      <v-btn
        class="mx-1" 
        v-for="items in socialIcons"
        :key="items.name"
        :color="items.color" fab small depressed dark>
        <v-icon dark>mdi-{{ items.icon }}</v-icon>
      </v-btn>
      </v-row>
    </v-container>

      <v-list dense>
        <v-divider
          class="mx-4"
          :inset="inset"
        ></v-divider>
      
        <v-list-item link v-for="link in links" :key="link.name">
          <v-list-item-action>
            <v-icon>mdi-{{ link.icon }}</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title> {{ link.name }} </v-list-item-title>
          </v-list-item-content>
        </v-list-item>

      </v-list>
    </v-navigation-drawer>

    <v-app-bar
      dark
      app
      flat
      color="black"
    >
      <v-app-bar-nav-icon @click="drawer = !drawer" />
      <v-spacer></v-spacer>
      <v-toolbar-title>FEMORA</v-toolbar-title>
      <v-spacer></v-spacer>
    </v-app-bar>
  </nav>
</template>


<script>
export default {
  name: 'Navbar',
  data() {
    return {
      links: [
        { name: 'Home', link: '/', icon: 'home' },
        { name: 'Portfolio', link: '/', icon: 'bag-carry-on' },
        { name: 'Pricing', link: '/', icon: 'currency-ngn' },
        { name: 'Contact', link: '/', icon: 'message-bulleted' },
      ],
      drawer: false,
      socialIcons: [
        { name: 'Facebook', link: '/', icon: 'facebook', color: 'blue darken-3' },
        { name: 'Facebook', link: '/', icon: 'twitter', color: 'blue' },
        { name: 'Facebook', link: '/', icon: 'youtube', color: 'red' },
        { name: 'Facebook', link: '/', icon: 'facebook', color: 'white' },
        { name: 'Facebook', link: '/', icon: 'facebook', color: 'white' },

      ]
    }
  },
}
</script>