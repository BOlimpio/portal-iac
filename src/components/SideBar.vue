<template>
    <nav>
      <v-navigation-drawer app v-model="drawer" :mini-variant.sync="mini" permanent>
        <v-list-item class="px-2">
          <v-list-item-avatar>
            <v-img src="https://randomuser.me/api/portraits/men/85.jpg"></v-img>
          </v-list-item-avatar>
  
          <v-list-item-title class="sidebar-username">
            <span class="text-h6 font-weight-bold">John Leider</span>
          </v-list-item-title>
  
          <v-btn icon @click.stop="mini = !mini">
            <v-icon class="sidebar-icon">mdi-chevron-left</v-icon>
          </v-btn>
        </v-list-item>
  
        <v-divider></v-divider>
  
        <v-list dense>
          <v-list-item v-for="item in items" :key="item.title" link @click="navigateToPage(item.route)">
            <v-list-item-icon>
              <v-icon class="sidebar-icon">{{ item.icon }}</v-icon>
            </v-list-item-icon>
  
            <v-list-item-content>
              <v-list-item-title class="text-h6 sidebar-title">{{ item.title }}</v-list-item-title>
            </v-list-item-content>
          </v-list-item>
        </v-list>
      </v-navigation-drawer>
    </nav>
  </template>
  
  <script>
  export default {
    data() {
      return {
        drawer: false,
        items: [
          { title: 'Dashboard', icon: 'dashboard', route: '/' },
          { title: 'Blogs Post', icon: 'mdi-typewriter', route: '/blogs' },
          { title: 'Contact', icon: 'mdi-chat-processing', route: '/contact' },
        ],
        mini: true,
      };
    },
    methods: {
      navigateToPage(route) {
        if (route === this.$route.path) {
          // Recarregar a página atual
          // location.reload();
        } else {
          this.$router.push(route);
        }
      },
    },
  };
  </script>
  
  <style scoped>
  .sidebar-username {
    font-size: 18px;
    color: #3f51b5;
  }
  
  .sidebar-icon {
    font-size: 24px;
    color: black;
  }
  
  .sidebar-title {
    font-size: 25px;
    color: black;
  }
  
  /* Resto dos seus estilos */
  </style>
  