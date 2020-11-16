<template>
  <div id="appbar">
    <v-app-bar
      :clipped-left="$vuetify.breakpoint.lgAndUp"
      color="blue-grey darken-4"
      app
      dark
    >
      <div class="d-flex align-center">
        <v-img
          alt="Vuetify Logo"
          class="shrink mr-2"
          contain
          src="https://cdn.vuetifyjs.com/images/logos/vuetify-logo-dark.png"
          transition="scale-transition"
          width="40"
        />

        <p class="headline mt-auto mb-auto font-weight-medium">Hotel HRIS</p>
      </div>

      <v-spacer></v-spacer>

      <v-btn icon>
        <v-icon>mdi-bell</v-icon>
      </v-btn>
      <p class="title mt-auto mb-auto font-weight-regular">Hello User</p>
      <v-btn icon>
        <v-icon>mdi-account-circle</v-icon>
      </v-btn>
    </v-app-bar>
  </div>
</template>
