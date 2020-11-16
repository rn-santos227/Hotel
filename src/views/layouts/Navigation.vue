<template>
  <div v-if="show">
    <v-navigation-drawer
      color="blue-grey darken-4"
      v-model="drawer"
      :clipped="$vuetify.breakpoint.lgAndUp"
      :mini-variant.sync="mini"
      app
      dark
    >
      <v-list-item class="px-2 nav_head">
        <v-list-item-avatar>
          <v-icon>mdi-view-headline</v-icon>
        </v-list-item-avatar>
        <v-list-item-title>
          <h3>NAVIGATION</h3>
        </v-list-item-title>
        <v-btn icon @click.stop="mini = !mini">
          <v-icon>mdi-chevron-left</v-icon>
        </v-btn>
      </v-list-item>
      <v-list dense>
        <template v-for="(item, key) in items">
          <v-list-group
            class="nav_position"
            :key="key"
            :prepend-icon="item.icon"
            append-icon=""
          >
            <template v-slot:activator>
              <router-link class="nav_text" :to="item.link">
                <v-list-item-content>
                  <v-list-item-title class="white--text">
                    {{ item.title }}
                  </v-list-item-title>
                </v-list-item-content>
              </router-link>
            </template>
          </v-list-group>
        </template>
      </v-list>
    </v-navigation-drawer>
  </div>
</template>

<script>
export default {
  data: () => ({
    temp_width: 0,
    drawer: null,
    mini: false,
    show: true,
    items: [
      {
        title: "Dashboard",
        icon: "mdi-view-dashboard",
        link: "/"
      },
      {
        title: "Reservations",
        icon: "mdi-bed",
        link: "/assets"
      },
      {
        title: "Inventory",
        icon: "mdi-clipboard-file",
        link: "/fleet"
      },
      {
        title: "Accounts",
        icon: "mdi-clipboard-account",
        link: "/staff"
      },
      {
        title: "Sales Report",
        icon: "mdi-chart-bar",
        link: "/reports"
      }
    ]
  })
};
</script>

<style scoped>
.nav_position {
  margin-left: -20px;
}

.nav_text {
  text-decoration: none;
}
</style>
