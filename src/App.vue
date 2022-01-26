<template>
  <v-app>
    <v-app-bar app color="white--text font-weight-light" dark>
      <a href="/" class="header-info">
        <div class="d-flex align-center">
          <v-img
            alt="Logo"
            class="shrink mr-2"
            contain
            src="./assets/logo.png"
            transition="scale-transition"
            width="40"
          />
          <h1 id="logo-name">Notes</h1>
          <v-spacer></v-spacer>
        </div>
      </a>
      <nav-bar />
    </v-app-bar>

    <v-main>
      <router-view />
    </v-main>

    <v-footer padless color="yellow darken-2 white--text">
      <v-col class="text-center" cols="12">
        {{ new Date().getFullYear() }} —
        <strong>&copy; The Googler Notes</strong>
      </v-col>
    </v-footer>
    <v-spacer></v-spacer>
  </v-app>
</template>

<script>
import NavBar from "./components/NavBar.vue";

export default {
  name: "App",

  data: () => ({
    //
  }),

  components: {
    NavBar,
  },
};
</script>

<style lang="scss">
@import url("https://fonts.googleapis.com/css2?family=Dongle:wght@300&display=swap");

.application,
.v-application {
  font-family: "Dongle", Arial, sans-serif;

  .v-toolbar__content {
    display: flex;
    justify-content: space-between;
  }

  header a {
    color: #ffffff;
    margin: 0.4em;
    text-decoration: none;

    &:hover {
      text-decoration: underline;
    }
  }

  .header-info {
    color: #ffffff;
    text-decoration: none;

    h1 {
      font-weight: lighter;
    }
  }

  form.v-form {
    width: 40em;
    margin: 2em auto;
  }

  .v-main {
    margin: 4em auto;
    width: 95%;

    .v-card {
      margin: 1em;

      .hashtag {
        padding: 0.5em 1em;
      }
    }

    .v-btn--fab.v-size--small.v-btn--absolute.v-btn--top {
      top: -45px;
      left: 2em;
    }

    @media (max-width: 700px) {
      .v-btn--fab.v-size--small.v-btn--absolute.v-btn--top {
        top: -20px;
        right: 15%;
      }
    }
  }

  @media (max-width: 700px) {
    .v-main {
      width: 80%;
    }
  }

  .v-footer {
    position: absolute;
    bottom: 0;
    width: 100%;
  }
}
</style>
