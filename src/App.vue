<template>
  <v-app>
    <v-main>
      <side-bar></side-bar>
      <router-view />
    </v-main>
  </v-app>
</template>

<script>
import SideBar from "@/components/SideBar.vue"; // Importe o componente SideBar aqui

export default {
  name: "App",

  components: {
    SideBar, // Registre o componente SideBar aqui
  },

  // ...
};
</script>
