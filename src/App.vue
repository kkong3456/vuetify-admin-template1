<template>
  <v-app>
    <v-app-bar
      app
      color="primary"
      dark
    >
    <v-app-bar-nav-icon v-on:click="drawer=!drawer"></v-app-bar-nav-icon>

    <v-spacer></v-spacer>


    </v-app-bar>

    <v-navigation-drawer app v-model="drawer">
      <v-list-item>
        <v-list-item-content>
          <v-list-item-title class="text-h6">
            Application
          </v-list-item-title>
          <v-list-item-subtitle>
            subtext
          </v-list-item-subtitle>
        </v-list-item-content>
      </v-list-item>

    <v-divider></v-divider>
    <v-list
      nav
      dense
    >
      <v-list-item
        v-for="item in items"
        :key="item.title"
        link
        :to="item.to"
      >
        <v-list-item-icon>
          <v-icon>{{ item.icon }}</v-icon>
        </v-list-item-icon>
        <v-list-item-content>
          <v-list-item-title>{{ item.title }}</v-list-item-title>
        </v-list-item-content>
      </v-list-item>
    </v-list>
  </v-navigation-drawer>

    <v-main>
      <v-container fluid>
        <router-view/>
      </v-container>
    </v-main>
  </v-app>
</template>

<script>

export default {
  name: 'App',

  data: () => ({
    drawer:false,
    items:[
      {title:'Dash-board',icon:'mdi-view-dashboard',to:'/'},
      {title:'GridSystem',icon:'mdi-image',to:'/grid-system/'},
      {title:'GridListPage',icon:'mdi-image',to:'/grid-list-page'},
      {title:'Break Points',icon:'mdi-image',to:'/breakpoints'}
    ],
    right:null,
    //
  }),
};
</script>
