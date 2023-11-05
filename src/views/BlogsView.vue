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
                      Blog Posts
                    </v-list-item-title>
                  </v-list-item-content>
                </v-list-item>
              </v-col>
            </v-row>
          </v-card>
        </v-col>
      </v-row>

      <v-row>
        <v-col cols="12" sm="6" md="12" v-for="(post, index) in blogPosts" :key="index">
          <v-card elevation="10" class="blog-post-card rounded-xl ml-4" color="grey lighten-3" flat>
            <v-row>
              <v-col cols="1">
                <v-img :src="post.image" alt="Blog Post" class="blog-post-image"
                  style="max-width: 150px; max-height: 150px;"></v-img>
              </v-col>
              <v-col cols="11">
                <v-card-title class="blog-post-title">
                  <span class="text-h6 font-weight-medium">{{ post.title }}</span>
                </v-card-title>
                <v-card-subtitle class="blog-post-date">
                  {{ post.date }}
                </v-card-subtitle>
                <v-divider></v-divider>
                <v-card-text class="blog-post-content">
                  {{ post.content }}
                </v-card-text>
                <v-card-actions class="blog-post-actions">
                  <v-btn outlined class="blog-post-learn-btn" @click="openLink(post.link)">
                    <v-icon left class="blog-post-learn-icon">mdi-link</v-icon>
                    Learn more
                  </v-btn>
                </v-card-actions>
              </v-col>
            </v-row>
          </v-card>
        </v-col>
      </v-row>
    </v-container>
  </v-app>
</template>

<script>
import axios from 'axios';

export default {
  name: 'BlogPosts',

  data() {
    return {
      blogPosts: [],
    };
  },

  mounted() {
    // Substitua 'sua_lambda_url_aqui' pela URL de sua lambda que retorna os dados dos blogs
    const lambdaUrl = 'https://{url_var}/api/v1/get_portal_data?folder_name=blogs-post';

    axios.get(lambdaUrl)
      .then(response => {
        this.blogPosts = JSON.parse(response.data.body);
      })
      .catch((error) => {
        console.error('Erro ao buscar os dados da lambda:', error);
      });
  },

  methods: {
    openLink(link) {
      // Abre o link do blog em uma nova aba/janela
      window.open(link, '_blank');
    }
  }
}
</script>

<style scoped>
.blog-post-card {
  margin: 1rem;
  padding: 1rem;
  display: flex;
  flex-direction: column;
}

.blog-post-image {
  width: 120px;
  height: 120px;
  object-fit: cover;
  border-radius: 15px;
}

.blog-post-title {
  color: #3f51b5;
  margin-top: 0.5rem;
}

.blog-post-date {
  font-size: 14px;
  color: #777;
}

.blog-post-content {
  font-size: 16px;
}

.blog-post-actions {
  display: flex;
  justify-content: right;
  align-items: right;
  margin-top: 0.5rem;
}

.blog-post-learn-btn {
  background-color: #B98AE5;
  color: white;
  min-width: 140px;
  transition: background-color 0.3s, color 0.3s;
}

.blog-post-learn-btn:hover {
  background-color: transparent;
  color: #B98AE5;
}

.blog-post-learn-icon {
  color: white;
}
</style>
