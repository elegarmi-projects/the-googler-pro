<template v-slot:extension>
  <div>
    <v-fab-transition>
      <v-btn color="blue" fab dark small absolute top @click="dialog = !dialog">
        <v-icon>mdi-plus</v-icon>
      </v-btn>
    </v-fab-transition>
    <v-dialog v-model="dialog" max-width="500px">
      <v-card>
        <v-card-text>
          <v-text-field label="Title"></v-text-field>

          <v-text-field label="Description"></v-text-field>

          <v-text-field label="Hashtag"></v-text-field>

          <small class="grey--text">* This doesn't actually save.</small>
        </v-card-text>

        <v-card-actions>
          <v-spacer></v-spacer>

          <v-btn text color="primary" @click="dialog = false"> Submit </v-btn>
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
