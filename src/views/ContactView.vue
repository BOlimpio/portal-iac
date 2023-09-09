<template>
  <v-app id="inspire">
    <v-container fluid class="mlmr-4 mt-5">
      <v-row>
        <v-col cols="12">
          <v-card class="rounded-xl pa-4" color="grey lighten-3" flat>
            <v-row>
              <v-col cols="12">
                <v-list-item one-line>
                  <v-list-item-content>
                    <v-list-item-title class="text-h5 mb-1">
                      Developers
                    </v-list-item-title>
                  </v-list-item-content>
                </v-list-item>
              </v-col>
            </v-row>
          </v-card>
        </v-col>
      </v-row>

      <v-row>
        <v-col cols="12" sm="4" v-for="(developer, index) in developers" :key="index">
          <v-card elevation="10" class="developer-card rounded-xl ml-4" color="grey lighten-3" flat>
            <v-avatar size="120">
              <img :src="developer.image" alt="Developer">
            </v-avatar>
            <v-card-title class="developer-name">
              <span class="text-h4 font-weight-medium">{{ developer.name }}</span>
            </v-card-title>
            <v-card-text>
              <span style="font-size: 22px; color: #3f51b5">{{ developer.role }}</span>
            </v-card-text>
            <v-card-text>
              <span style="font-size: 18px; color: black">{{ developer.summary }}</span>
            </v-card-text>
            <v-card-actions class="developer-actions">
              <v-btn icon class="developer-linkedin-btn" @click="openLinkedIn(developer.linkedin)">
                <v-icon color="white">mdi-linkedin</v-icon>
              </v-btn>
            </v-card-actions>
            <v-divider></v-divider>
            <v-card-actions class="developer-chips">
              <v-chip-group>
                <v-chip v-for="(skill, idx) in developer.skills" :key="idx" color="#B98AE5" small>
                  <v-icon left small>mdi-check-circle</v-icon>
                  {{ skill }}
                </v-chip>
              </v-chip-group>
            </v-card-actions>
          </v-card>
        </v-col>
      </v-row>
    </v-container>
  </v-app>
</template>

<script>

export default {
  name: 'Home',

  components: {

  },

  data() {
    return {
      // Example data for developers
      developers: [
        {
          name: 'John Doe',
          role: 'Software Engineer',
          summary: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Pellentesque maximus mattis pellentesque. Nulla a fringilla lorem. Quisque elementum augue ut egestas porttitor. Proin nisl dui, vulputate nec erat pulvinar, vulputate.',
          linkedin: 'https://www.linkedin.com/in/johndoe',
          skills: ['JavaScript', 'Vue.js', 'Node.js'],
          image: 'https://cdn.vuetifyjs.com/images/lists/1.jpg'
        },
        {
          name: 'Jane Smith',
          role: 'Frontend Developer',
          summary: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Pellentesque maximus mattis pellentesque. Nulla a fringilla lorem. Quisque elementum augue ut egestas porttitor. Proin nisl dui, vulputate nec erat pulvinar, vulputate.',
          linkedin: 'https://www.linkedin.com/in/janesmith',
          skills: ['HTML', 'CSS', 'React'],
          image: 'https://cdn.vuetifyjs.com/images/lists/2.jpg'
        },
        {
          name: 'Jane Smith',
          role: 'Frontend Developer',
          summary: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Pellentesque maximus mattis pellentesque. Nulla a fringilla lorem. Quisque elementum augue ut egestas porttitor. Proin nisl dui, vulputate nec erat pulvinar, vulputate.',
          linkedin: 'https://www.linkedin.com/in/janesmith',
          skills: ['HTML', 'CSS', 'React'],
          image: 'https://cdn.vuetifyjs.com/images/lists/2.jpg'
        },
        // Add more developers here
      ]
    }
  },

  methods: {
    openLinkedIn(link) {
      // Open the LinkedIn profile in a new tab/window
      window.open(link, '_blank');
    }
  }
}
</script>

<style>
.developer-card {
  margin: 1rem;
  padding: 1rem;
  display: flex;
  flex-direction: column;
  align-items: center;
}

.developer-name {
  text-align: center;
  margin-top: 0.5rem;
  color: #3f51b5;
}

/* .developer-role {
  font-size: 20px;
  color: #3f51b5;
} */

.developer-summary {
  font-size: 14px;
}

.developer-actions {
  display: flex;
  justify-content: center;
  align-items: center;
  margin-top: 0.5rem;
}

.developer-linkedin-btn {
  background-color: #0077b5;
}

.developer-linkedin-icon {
  color: #3f51b5;
}

.developer-chips .v-chip {
  font-size: 18px;
}
</style>
