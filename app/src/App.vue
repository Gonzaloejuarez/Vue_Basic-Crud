<template>
  <v-app>
    <v-navigation-drawer
      v-model="drawer"
      absolute
      temporary
      app clipped
    >
      <v-list>
        <v-list-item :to="{path: '/'}">
          <v-list-item-action >
            <v-icon>mdi-{{icons[0] }}</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title>Inicio</v-list-item-title>
          </v-list-item-content>
        </v-list-item>

           <v-list-item :to="{path: '/articulos'}">
          <v-list-item-action>
            <v-icon>mdi-{{icons[1] }}</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title>Articulos</v-list-item-title>
          </v-list-item-content>
           </v-list-item>

             <v-list-item :to="{path: '/contacto'}">
          <v-list-item-action>
            <v-icon>mdi-{{icons[1] }}</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title>Contacto</v-list-item-title>
          </v-list-item-content>
           </v-list-item>
      </v-list>  
    </v-navigation-drawer>
  <v-card class="mx auto overflow-hidden" height="100%" width="100%">
    <v-system-bar color="deep-purple darken=3"></v-system-bar>
    <v-app-bar class="deep-purple accent-4 white--text">
      <v-app-bar-nav-icon @click="drawer=true" class="white--text"></v-app-bar-nav-icon>
        <v-toolbar-tittle>
          <v-list-item :to="{path: '/'}">
          <v-img
          alt="Vuetify Logo"
          class="shrink mr-2"
          contain
          transition="scale-transition"
          ></v-img>
          </v-list-item>
        </v-toolbar-tittle>
    </v-app-bar>

    <v-main>
      <v-container fluid>
        <v-fade-transition mode="out in">
          <router-view></router-view>
        </v-fade-transition>
      </v-container>
    </v-main>
  </v-card>
  </v-app>
</template>

<script>
  export default {
   name: 'App',
   data: () => ({
     icons : ['home', 'shopping', 'email'],
     drawer: false,
    }),

  };
</script>