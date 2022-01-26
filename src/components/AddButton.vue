<template v-slot:extension>
  <div>
    <v-fab-transition>
      <v-btn color="blue" fab dark small absolute top @click="dialog = !dialog">
        <v-icon>mdi-plus</v-icon>
      </v-btn>
    </v-fab-transition>
    <v-dialog v-model="dialog" max-width="500px">
      <v-card class="amber lighten-4 rounded">
        <v-card-text class="pt-2">
          <v-text-field
            label="Title"
            color="orange orange-darken-4"
          ></v-text-field>

          <v-text-field
            label="Description"
            color="orange orange-darken-4"
          ></v-text-field>

          <v-text-field
            label="Hashtag"
            color="orange orange-darken-4"
          ></v-text-field>

          <small class="grey--text">* This doesn't actually save.</small>
        </v-card-text>

        <v-card-actions>
          <v-spacer></v-spacer>

          <v-btn text color="orange orange-darken-4" @click="dialog = false">
            Submit
          </v-btn>
        </v-card-actions>
      </v-card>
    </v-dialog>
  </div>
</template>

<script>
export default {
  name: "AddButton",
};
</script>

<script>
export default {
  data() {
    return {
      dialog: false,
    };
  },
};
</script>
