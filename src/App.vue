<template>
  <v-app>
    <v-main>
        <top-menu></top-menu>
      <router-view />
    </v-main>
  </v-app>
</template>

<script>

import TopMenu from "@/components/TopMenu.vue";

export default {
  name: "App",

  components: {
    TopMenu,
  },

  // ...
};
</script>
