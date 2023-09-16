<template>
  <v-app id="inspire">
    <v-container fluid class="mlmr-4">
      <v-app-bar color="rgba(0,0,0,0)" flat>

        <v-text-field label="Search ..." class="pt-5" filled prepend-inner-icon="mdi-magnify" dense solo flat
          background-color="grey lighten-4" rounded></v-text-field>
        <v-spacer></v-spacer>

      </v-app-bar>

      <v-row>
        <v-col cols="12" sm="9">
          <v-card class="mx-4 rounded-xl pa-4" color="grey lighten-3" flat>
            <v-row>
              <v-col cols="12" sm="12">
                <v-list-item one-line>
                  <v-list-item-content>
                    <v-list-item-title class="text-h5 mb-1">
                      Modules creatades with Terraform!
                    </v-list-item-title>
                  </v-list-item-content>
                </v-list-item>
              </v-col>
            </v-row>
          </v-card>
          <v-toolbar flat color="rgba(0,0,0,0)" dense class="mt-n1">
            <span>Add chip filters here -> AWS / Azure / Done / etc</span>
          </v-toolbar>
          <v-row class="mt-n5">
            <v-col cols="12" sm="4" v-for="module in modules" :key="module.title">
              <v-card elevation="10" class="rounded-xl ml-4" color="grey lighten-3" flat>
                <v-img src="../assets/terraform.png" height="140px"></v-img>
                <v-card-title>
                  <span class="text-h6 font-weight-light">{{ module.title }}</span>
                </v-card-title>
                <v-card-text class="">
                  {{ module.description }}
                </v-card-text>
                <v-divider class="mx-4"></v-divider>
                <v-card-text>
                  <v-chip-group>
                    <v-chip color="indigo">{{ module.status }}</v-chip>
                    <v-chip color="orange">{{ module.cloud_provider }}</v-chip>
                    <v-chip color="primary">{{ module.version }}</v-chip>
                  </v-chip-group>
                </v-card-text>


                <v-card-actions class="mt-n7">
                  <v-list-item class="">
                    <!-- Avatar dos desenvolvedores -->
                    <div color="grey darken-3">
                      <v-avatar v-for="(developer, devIndex) in module.developers" :key="devIndex" class="ml-n3" size="30">
                        <img :src="getDeveloperAvatar(developer)" :alt="developer">
                      </v-avatar>
                    </div>
                    <v-row align="center" justify="end">
                      <!-- <v-btn outlined class="blog-post-learn-btn mr-2" @click="openLink(post.link)">
                        <v-icon left class="blog-post-learn-icon">mdi-download</v-icon>
                        Download
                      </v-btn> -->
                      <v-btn outlined class="blog-post-learn-btn mr-2" @click="downloadHowToUse(module.github_link)">
                        <v-icon left class="blog-post-learn-icon">mdi-download</v-icon>
                        Download
                      </v-btn>
                      <v-btn outlined class="blog-post-learn-btn" @click="openGithubLink(module.github_link)">
                        <v-icon left class="blog-post-learn-icon">mdi-file-document</v-icon>
                        Docs
                      </v-btn>
                    </v-row>
                  </v-list-item>
                </v-card-actions>
              </v-card>
            </v-col>
          </v-row>
        </v-col>
        <v-col cols="12" sm="3" class="d-flex justify-end">
          <v-card class=" rounded-xl pa-4" color="grey lighten-3" flat>
            <v-card-title>
              <span class="text-h6 font-weight-light">Key numbers:</span>
            </v-card-title>
            <v-app-bar color="rgba(0,0,0,0)" tile>
              <v-btn tile fab small color="orange lighten-4" elevation="0">
                <v-icon color="black">fas fa-book</v-icon>
              </v-btn>
              <strong class="subtitle black--text ml-2">
                Blogs post <span class="caption"><br><v-chip color="#A26BD5">14 Azure</v-chip></span>
              </strong>
              <v-spacer></v-spacer>
            </v-app-bar>
            <v-app-bar color="rgba(0,0,0,0)" tile class="mt-3">
              <v-btn tile fab small color="green lighten-4" elevation="0">
                <v-icon color="black">fas fa-hands-wash</v-icon>
              </v-btn>
              <strong class="subtitle black--text ml-2">
                Modules in progress <span class="caption"><br><v-chip color="blue">3 Azure</v-chip> <v-chip
                    color="orange">4 AWS</v-chip></span>
              </strong>
              <v-spacer></v-spacer>
            </v-app-bar>
            <v-app-bar color="rgba(0,0,0,0)" tile class=mt-3>
              <v-btn tile fab small color="blue lighten-4" elevation="0">
                <v-icon color="black">fas fa-user-friends</v-icon>
              </v-btn>
              <strong class="subtitle black--text ml-2">
                Modules done <span class="caption"><br><v-chip color="blue">10 Azure</v-chip> <v-chip color="orange">10
                    AWS</v-chip></span>
              </strong>
              <v-spacer></v-spacer>
            </v-app-bar>
          </v-card>
        </v-col>
      </v-row>
    </v-container>
  </v-app>
</template>

<script>
import axios from 'axios';

export default {
  name: 'Home',

  data() {
    return {
      modules: [],
    };
  },

  mounted() {
    // Aqui você coloca a URL da sua lambda
    const lambdaUrl = 'https://5eglyiyxvmrvx5rhjbteq76tfi0fkoav.lambda-url.us-east-1.on.aws/';

    axios.get(lambdaUrl)
      .then(response => {
        this.modules = response.data;
      })
      .catch((error) => {
        console.error('Erro ao buscar os dados da lambda:', error);
      });
  },

  methods: {
    // Esta função retorna o URL do avatar com base no nome do desenvolvedor
    getDeveloperAvatar(developer) {
      // Use o objeto de avatares que você carregou
      const avatarFileName = developer.trim() + '.jpeg';
      return require(`@/assets/team/${avatarFileName}`);
    },
    openGithubLink(link) {
      if (link) {
        // Abre o link do GitHub em uma nova janela ou guia
        window.open(link, "_blank");
      }
    },
    downloadHowToUse(repoLink) {
      // Aqui você fará uma solicitação para a sua Lambda de download,
      // passando o nome do repositório como parâmetro
      const fullRepoName = repoLink.split("github.com/")[1]; // Pega tudo após "github.com/"
      const lambdaUrldownload = `https://7jid3aqo5cotckyoipwkzv75pm0uvtvi.lambda-url.us-east-1.on.aws/?repo_name=${fullRepoName}`;


      axios.get(lambdaUrldownload)
        .then(response => {
          // O retorno da Lambda será o arquivo ZIP codificado em base64
          const zipContent = response.data.zip_content;
          const fileName = response.data.file_name;

          // Crie um elemento "a" para criar um link de download
          const link = document.createElement('a');
          link.href = `data:application/zip;base64,${zipContent}`;
          link.download = fileName;
          link.click();
        })
        .catch((error) => {
          console.error('Erro ao baixar o arquivo:', error);
        });
    },
  },
};
</script>

<style>
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
