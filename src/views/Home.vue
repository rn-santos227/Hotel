<template>
  <div class="home">
    <v-container fluid>
      <v-row class="text-left">
        <v-flex x12>
          <v-card flat>
            <v-card-text>
              <v-row class="ml-4">
                <v-flex class="pa-2" xs3>
                  <v-text-field
                    v-model="room"
                    label="Room Number"
                    hint="Enter Room Number"
                  />
                </v-flex>
                <v-flex class="pa-2" xs3>
                  <v-select
                    v-model="status"
                    :items="status_list"
                    label="Room Status"
                    hint="Select Room Status"
                  ></v-select>
                </v-flex>
                <v-flex class="pa-2" xs3>
                  <v-select
                    v-model="arrangement"
                    :items="arrangement_list"
                    label="Sorted By"
                    hint="Select sort viewing"
                  ></v-select>
                </v-flex>
                <v-flex class="pa-2" xs3>
                  <v-btn class="mx-2" fab dark small color="blue-grey darken-4">
                    <v-icon dark>
                      mdi-magnify
                    </v-icon>
                  </v-btn>
                  <v-btn class="mx-2" fab dark small color="blue-grey darken-4">
                    <v-icon dark>
                      mdi-close
                    </v-icon>
                  </v-btn>
                </v-flex>
              </v-row>
              <v-row class="ml-4 mt-4">
                <v-card
                  v-for="(room, key) in rooms"
                  :key="key"
                  class="ma-3 pa-3"
                  exact
                  :color="getCardColor(room.status)"
                >
                  <v-card-title class="white--text">
                    Room: {{ room.number }}
                  </v-card-title>
                  <v-card-text align="center">
                    <v-icon dark size="75">{{ getIcon(room.status) }}</v-icon>
                    <p class="title white--text">{{ room.status }}</p>
                  </v-card-text>
                  <v-card-actions>
                    <v-btn class="mx-2" fab small color="white">
                      <v-icon>
                        mdi-magnify
                      </v-icon>
                    </v-btn>
                    <v-btn class="mx-2" fab small color="white">
                      <v-icon>
                        mdi-notebook
                      </v-icon>
                    </v-btn>
                    <v-btn class="mx-2" fab small color="white">
                      <v-icon>
                        mdi-cog
                      </v-icon>
                    </v-btn>
                  </v-card-actions>
                </v-card>
              </v-row>
            </v-card-text>
          </v-card>
        </v-flex>
      </v-row>
    </v-container>
  </div>
</template>

<script>
// @ is an alias to /src

export default {
  name: "Home",
  data: () => ({
    room: "",
    status: "All",
    arrangement: "Accomodation",
    status_list: ["All", "Vacant", "Occupied", "Maintenance"],
    arrangement_list: [
      "Accomodation",
      "All",
      "Vacant",
      "Occupied",
      "Maintenance"
    ],
    rooms: [
      { number: "501", status: "Vacant" },
      { number: "502", status: "Maintenance" },
      { number: "503", status: "Vacant" },
      { number: "504", status: "Vacant" },
      { number: "505", status: "Occupied" },
      { number: "506", status: "Vacant" },
      { number: "507", status: "Reserved" },
      { number: "508", status: "Vacant" },
      { number: "509", status: "Occupied" },
      { number: "510", status: "Vacant" },
      { number: "511", status: "vacant" },
      { number: "512", status: "Reserved" }
    ]
  }),
  methods: {
    getCardColor(status) {
      let color = "green";
      switch (status) {
        case "Vacant":
          color = "green";
          break;
        case "Reserved":
          color = "blue";
          break;
        case "Maintenance":
          color = "orange";
          break;
        case "Occupied":
          color = "red";
          break;
      }
      return color;
    },
    getIcon(status) {
      let icon = "mdi-bed-empty";
      switch (status) {
        case "Vacant":
          icon = "mdi-bed-empty";
          break;
        case "Reserved":
          icon = "mdi-calendar-check";
          break;
        case "Maintenance":
          icon = "mdi-broom";
          break;
        case "Occupied":
          icon = "mdi-bed";
          break;
      }
      return icon;
    }
  }
};
</script>
