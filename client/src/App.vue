<template>
  <v-app>
    <!-- Navbar -->
    <v-app-bar app color="white" elevate-on-scroll fixed height="70">
      <v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>

      <v-toolbar-title
        ><img src="@/assets/logo.png" class="mt-3" height="50"
      /></v-toolbar-title>
      <v-spacer></v-spacer>

      <v-btn icon>
        <v-icon>mdi-heart</v-icon>
      </v-btn>

      <v-btn icon>
        <v-icon @click="search = !search">mdi-magnify</v-icon>
      </v-btn>
      <v-col cols="3" sm="3" v-if="search">
        <v-text-field
          width="10"
          hint
          label="Search"
          single-line
          hide-details
        ></v-text-field>
      </v-col>

      <v-menu left bottom>
        <template v-slot:activator="{ on, attrs }">
          <v-btn icon v-bind="attrs" v-on="on">
            <v-icon>mdi-dots-vertical</v-icon>
          </v-btn>
        </template>

        <v-list>
          <v-list-item v-for="n in 5" :key="n" @click="() => {}">
            <v-list-item-title>Option {{ n }}</v-list-item-title>
          </v-list-item>
        </v-list>
      </v-menu>
    </v-app-bar>

    <v-navigation-drawer color="white" v-model="drawer" statless app>
      <v-list nav>
        <v-list-item to="/">
          <v-list-item-icon>
            <v-divider vertical color="red"></v-divider>
          </v-list-item-icon>
          <v-list-item-title class="title">Karrieretag</v-list-item-title>
        </v-list-item>
        <v-list-item to="/infos" justify-center>
          <v-list-item-title class="title">Karrieretag</v-list-item-title>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <!-- Navbar -->

    <v-main hide-overlay>
      <router-view />
    </v-main>
  </v-app>
</template>

<script>
export default {
  name: 'App',

  data: () => ({
    drawer: false,
    search: false,
  }),
};
</script>


