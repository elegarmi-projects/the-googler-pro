<template>
  <div>
    <a v-for="(link, i) in topLinks" :key="i" :href="link.href">
      {{ link.text }}
    </a>
  </div>
</template>

<script>
export default {
  name: "NavBar",

  data: () => ({
    topLinks: [
      {
        text: "Login",
        href: "/login",
      },
      {
        text: "Register",
        href: "/register",
      },
    ],
  }),
};
</script>
