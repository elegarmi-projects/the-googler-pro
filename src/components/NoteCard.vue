<template>
  <div class="row">
    <v-card
      v-for="(item, i) in cardsInfo"
      :key="i"
      class="mx-auto rounded amber lighten-4 col-lg-3 col-md-6 col-xs-12"
      max-width="344"
      elevation="4"
    >
      <v-list-item three-line>
        <v-list-item-content>
          <v-list-item-title class="text-h5 mb-1">{{
            item.title
          }}</v-list-item-title>
          <v-list-item-subtitle>{{ item.subtitle }}</v-list-item-subtitle>
        </v-list-item-content>
      </v-list-item>

      <p class="hashtag">{{ item.hashtag }}</p>

      <v-card-actions>
        <v-btn outlined text>Edit</v-btn>
        <v-btn outlined text>Delete</v-btn>
      </v-card-actions>
    </v-card>
  </div>
</template>

<script>
export default {
  name: "NoteCard",

  data: () => ({
    cardsInfo: [
      {
        title: "Individual challenge",
        subtitle: "The Googler",
        hashtag: "#challenge, #femhack",
      },
      {
        title: "Grupal challenge",
        subtitle: "Femhoot",
        hashtag: "#challenge, #femhack",
      },
      {
        title: "Bootcamp challenge",
        subtitle: "The Giaco Project",
        hashtag: "#challenge, #f5",
      },
      {
        title: "Grupal challenge",
        subtitle: "The Final Project",
        hashtag: "#challenge, #f5",
      },
    ],
  }),
};
</script>
