<template>
  <v-app id="inspire">
    <Navigation />
    <Appbar />
    <v-main class="blue-grey lighten-5">
      <v-container fluid>
        <router-view />
      </v-container>
    </v-main>
  </v-app>
</template>

<script>
import Appbar from "./views/layouts/Appbar";
import Navigation from "./views/layouts/Navigation";

export default {
  name: "App",

  components: {
    Appbar,
    Navigation
  },

  data: () => ({
    //
  })
};
</script>
