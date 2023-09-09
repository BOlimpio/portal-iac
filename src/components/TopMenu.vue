<template>
  <v-app-bar app color="primary" dark>
    <v-menu v-model="menu" offset-y>
      <template v-slot:activator="{ on }">
        <v-btn icon v-on="on">
          <v-icon>mdi-menu</v-icon>
        </v-btn>
      </template>
      <v-list>
        <v-list-item
          v-for="item in items"
          :key="item.route"
          @click="navigateTo(item.route)"
        >
          <v-list-item-icon>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-icon>
          <v-list-item-content>
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-menu>
    <v-toolbar-title>Portal IaC</v-toolbar-title>
    <v-spacer></v-spacer>

    <v-btn icon @click="navigateTo('/')">
      <v-icon>home</v-icon>
    </v-btn>
    <v-btn icon @click="navigateTo('/blogs')">
      <v-icon>mdi-typewriter</v-icon>
    </v-btn>
    <v-btn icon @click="navigateTo('/contact')">
      <v-icon>mdi-chat-processing</v-icon>
    </v-btn>
    
  </v-app-bar>
</template>

<script>
export default {
  data() {
    return {
      items: [
        { title: 'Dashboard', icon: 'mdi-view-dashboard', route: '/' },
        { title: 'Blogs Post', icon: 'mdi-typewriter', route: '/blogs' },
        { title: 'Contact', icon: 'mdi-chat-processing', route: '/contact' },
      ],
      menu: false,
    };
  },
  methods: {
    toggleMenu() {
      this.menu = !this.menu;
    },
    navigateTo(route) {
      if (route === this.$route.path) {
        // Recarregar a página atual
        // location.reload();
      } else {
        this.menu = false; // Fechar o menu ao clicar em uma opção
        this.$router.push(route);
      }

    },
  },
};
</script>
