<template>
  <v-app id="inspire">
    <v-navigation-drawer 
      v-model="drawer" 
      class="pt-5 text-center" 
      app
    >

      <v-avatar color="indigo">
        <v-icon dark >
        mdi-account-circle
        </v-icon>
      </v-avatar>
      <v-list-item>
        <v-list-item-content>
          <v-list-item-title class="text-h6"> Vue JS </v-list-item-title>
          <v-list-item-subtitle> Lista de Contats </v-list-item-subtitle>
        </v-list-item-content>
      </v-list-item>

      <v-divider></v-divider>

      <v-list dense nav>
        <v-list-item v-for="item in items" :key="item.title" :to="item.to" link>
          <v-list-item-icon>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-icon>

          <v-list-item-content>
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>

    <v-app-bar app>
      <v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>

      <v-toolbar-title>Application</v-toolbar-title>
    </v-app-bar>

    <v-main>
      <router-view></router-view>
    </v-main>

  </v-app>
</template>

<script>
  export default {
    data: () => ({ 
      drawer: false,
      items: [
          { title: 'Home', icon: 'mdi-view-dashboard', to: '/'},
          { title: 'Sobre', icon: 'mdi-help-box', to: '/sobre'},
        ],
    }),
  }
</script>