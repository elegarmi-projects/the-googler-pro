<template>
  <div>
    <add-button />
    <note-card />
  </div>
</template>

<script>
import AddButton from "../components/AddButton.vue";
import NoteCard from "../components/NoteCard.vue";

export default {
  name: "Home",

  components: {
    NoteCard,
    AddButton,
  },
};
</script>
