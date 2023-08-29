<template>
  <v-app id="inspire">
    <!-- <SideBar /> -->
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
            <v-col cols="12" sm="4">
              <v-card elevation="10" class="rounded-xl ml-4" color="grey lighten-3" flat>
                <v-img src="../assets/terraform.png" height="140px"></v-img>
                <v-card-title>
                  <span class="text-h6 font-weight-light">Prototyping</span>
                </v-card-title>

                <v-card-text class="">
                  Explanation about module Explanation about module Explanation about module Explanation about module
                  Explanation about module Explanation about module
                </v-card-text>
                <v-divider class="mx-4"></v-divider>
                <v-card-text>
                  <v-chip-group v-model="selectedChips">
                    <v-chip color="indigo">AWS</v-chip>
                    <v-chip color="orange">Done</v-chip>
                    <v-chip color="primary">v1.0</v-chip>
                  </v-chip-group>
                </v-card-text>


                <v-card-actions class="mt-n7">
                  <v-list-item class="">
                    <div color="grey darken-3">

                      <v-avatar class="ml-n3" size="30">
                        <img src="https://cdn.vuetifyjs.com/images/lists/1.jpg" alt="John">
                      </v-avatar>
                      <v-avatar class="ml-n3" size="30">
                        <img src="https://cdn.vuetifyjs.com/images/lists/3.jpg" alt="John">
                      </v-avatar>
                      <v-avatar class="ml-n3" size="30">
                        <img src="https://cdn.vuetifyjs.com/images/lists/4.jpg" alt="John">
                      </v-avatar>
                      <v-avatar class="ml-n3" size="30">
                        <img src="https://cdn.vuetifyjs.com/images/lists/2.jpg" alt="John">
                      </v-avatar>
                      <v-avatar class="ml-n3" color="black" size="30">
                        <span class="caption white--text">+1</span>
                      </v-avatar>
                    </div>



                    <v-row align="center" justify="end">
                      <v-btn outlined class="blog-post-learn-btn mr-2" @click="openLink(post.link)">
                        <v-icon left class="blog-post-learn-icon">mdi-download</v-icon>
                        Download
                      </v-btn>
                      <v-btn outlined class="blog-post-learn-btn" @click="openLink(post.link)">
                        <v-icon left class="blog-post-learn-icon">mdi-file-document</v-icon>
                        Docs
                      </v-btn>
                    </v-row>
                  </v-list-item>
                </v-card-actions>
              </v-card>
            </v-col>
            <v-col cols="12" sm="4">
              <v-card elevation="10" class="rounded-xl ml-4" color="grey lighten-3" flat>
                <v-img src="../assets/terraform.png" height="140px"></v-img>
                <v-card-title>
                  <span class="text-h6 font-weight-light">Prototyping</span>
                </v-card-title>

                <v-card-text class="">
                  Explanation about module Explanation about module Explanation about module Explanation about module
                  Explanation about module Explanation about module
                </v-card-text>
                <v-divider class="mx-4"></v-divider>
                <v-card-text>
                  <v-chip-group v-model="selectedChips">
                    <v-chip color="indigo">Azure</v-chip>
                    <v-chip color="orange">In progress</v-chip>
                    <v-chip color="primary">v1.0</v-chip>
                  </v-chip-group>
                </v-card-text>

                <v-card-actions class="mt-n7">
                  <v-list-item class="">
                    <div color="grey darken-3">

                      <v-avatar class="ml-n3" size="30">
                        <img src="https://cdn.vuetifyjs.com/images/lists/1.jpg" alt="John">
                      </v-avatar>
                      <v-avatar class="ml-n3" size="30">
                        <img src="https://cdn.vuetifyjs.com/images/lists/3.jpg" alt="John">
                      </v-avatar>
                      <v-avatar class="ml-n3" size="30">
                        <img src="https://cdn.vuetifyjs.com/images/lists/4.jpg" alt="John">
                      </v-avatar>
                      <v-avatar class="ml-n3" size="30">
                        <img src="https://cdn.vuetifyjs.com/images/lists/2.jpg" alt="John">
                      </v-avatar>
                      <v-avatar class="ml-n3" color="black" size="30">
                        <span class="caption white--text">+1</span>
                      </v-avatar>
                    </div>



                    <v-row align="center" justify="end">

                      <v-btn outlined class="blog-post-learn-btn" @click="openLink(post.link)">
                        <v-icon left class="blog-post-learn-icon">mdi-download</v-icon>
                        Download
                      </v-btn>

                    </v-row>
                  </v-list-item>
                </v-card-actions>
              </v-card>
            </v-col>
            <v-col cols="12" sm="4">
              <v-card elevation="10" class="rounded-xl ml-4" color="grey lighten-3" flat>
                <v-img src="../assets/terraform.png" height="140px"></v-img>
                <v-card-title>
                  <span class="text-h6 font-weight-light">Prototyping</span>
                </v-card-title>

                <v-card-text class="">
                  Explanation about module Explanation about module Explanation about module Explanation about module
                  Explanation about module Explanation about module
                </v-card-text>

                <v-card-actions class="mt-n7">
                  <v-list-item class="">
                    <div color="grey darken-3">

                      <v-avatar class="ml-n3" size="30">
                        <img src="https://cdn.vuetifyjs.com/images/lists/1.jpg" alt="John">
                      </v-avatar>
                      <v-avatar class="ml-n3" size="30">
                        <img src="https://cdn.vuetifyjs.com/images/lists/3.jpg" alt="John">
                      </v-avatar>
                      <v-avatar class="ml-n3" size="30">
                        <img src="https://cdn.vuetifyjs.com/images/lists/4.jpg" alt="John">
                      </v-avatar>
                      <v-avatar class="ml-n3" size="30">
                        <img src="https://cdn.vuetifyjs.com/images/lists/2.jpg" alt="John">
                      </v-avatar>
                      <v-avatar class="ml-n3" color="black" size="30">
                        <span class="caption white--text">+1</span>
                      </v-avatar>
                    </div>



                    <v-row align="center" justify="end">

                      <v-btn outlined class="blog-post-learn-btn" @click="openLink(post.link)">
                        <v-icon left class="blog-post-learn-icon">mdi-download</v-icon>
                        Download
                      </v-btn>

                    </v-row>
                  </v-list-item>
                </v-card-actions>
              </v-card>
            </v-col>
            <v-col cols="12" sm="4">
              <v-card elevation="10" class="rounded-xl ml-4" color="grey lighten-3" flat>
                <v-img src="../assets/terraform.png" height="140px"></v-img>
                <v-card-title>
                  <span class="text-h6 font-weight-light">Prototyping</span>
                </v-card-title>

                <v-card-text class="">
                  Explanation about module Explanation about module Explanation about module Explanation about module
                  Explanation about module Explanation about module
                </v-card-text>

                <v-card-actions class="mt-n7">
                  <v-list-item class="">
                    <div color="grey darken-3">

                      <v-avatar class="ml-n3" size="30">
                        <img src="https://cdn.vuetifyjs.com/images/lists/1.jpg" alt="John">
                      </v-avatar>
                      <v-avatar class="ml-n3" size="30">
                        <img src="https://cdn.vuetifyjs.com/images/lists/3.jpg" alt="John">
                      </v-avatar>
                      <v-avatar class="ml-n3" size="30">
                        <img src="https://cdn.vuetifyjs.com/images/lists/4.jpg" alt="John">
                      </v-avatar>
                      <v-avatar class="ml-n3" size="30">
                        <img src="https://cdn.vuetifyjs.com/images/lists/2.jpg" alt="John">
                      </v-avatar>
                      <v-avatar class="ml-n3" color="black" size="30">
                        <span class="caption white--text">+1</span>
                      </v-avatar>
                    </div>



                    <v-row align="center" justify="end">

                      <v-btn outlined class="blog-post-learn-btn" @click="openLink(post.link)">
                        <v-icon left class="blog-post-learn-icon">mdi-download</v-icon>
                        Download
                      </v-btn>

                    </v-row>
                  </v-list-item>
                </v-card-actions>
              </v-card>
            </v-col>
            <v-col cols="12" sm="4">
              <v-card elevation="10" class="rounded-xl ml-4" color="grey lighten-3" flat>
                <v-img src="../assets/terraform.png" height="140px"></v-img>
                <v-card-title>
                  <span class="text-h6 font-weight-light">Prototyping</span>
                </v-card-title>

                <v-card-text class="">
                  Explanation about module Explanation about module Explanation about module Explanation about module
                  Explanation about module Explanation about module
                </v-card-text>

                <v-card-actions class="mt-n7">
                  <v-list-item class="">
                    <div color="grey darken-3">

                      <v-avatar class="ml-n3" size="30">
                        <img src="https://cdn.vuetifyjs.com/images/lists/1.jpg" alt="John">
                      </v-avatar>
                      <v-avatar class="ml-n3" size="30">
                        <img src="https://cdn.vuetifyjs.com/images/lists/3.jpg" alt="John">
                      </v-avatar>
                      <v-avatar class="ml-n3" size="30">
                        <img src="https://cdn.vuetifyjs.com/images/lists/4.jpg" alt="John">
                      </v-avatar>
                      <v-avatar class="ml-n3" size="30">
                        <img src="https://cdn.vuetifyjs.com/images/lists/2.jpg" alt="John">
                      </v-avatar>
                      <v-avatar class="ml-n3" color="black" size="30">
                        <span class="caption white--text">+1</span>
                      </v-avatar>
                    </div>



                    <v-row align="center" justify="end">

                      <v-btn outlined class="blog-post-learn-btn" @click="openLink(post.link)">
                        <v-icon left class="blog-post-learn-icon">mdi-download</v-icon>
                        Download
                      </v-btn>

                    </v-row>
                  </v-list-item>
                </v-card-actions>
              </v-card>
            </v-col>
            <v-col cols="12" sm="4">
              <v-card elevation="10" class="rounded-xl ml-4" color="grey lighten-3" flat>
                <v-img src="../assets/terraform.png" height="140px"></v-img>
                <v-card-title>
                  <span class="text-h6 font-weight-light">Prototyping</span>
                </v-card-title>

                <v-card-text class="">
                  Explanation about module Explanation about module Explanation about module Explanation about module
                  Explanation about module Explanation about module
                </v-card-text>

                <v-card-actions class="mt-n7">
                  <v-list-item class="">
                    <div color="grey darken-3">

                      <v-avatar class="ml-n3" size="30">
                        <img src="https://cdn.vuetifyjs.com/images/lists/1.jpg" alt="John">
                      </v-avatar>
                      <v-avatar class="ml-n3" size="30">
                        <img src="https://cdn.vuetifyjs.com/images/lists/3.jpg" alt="John">
                      </v-avatar>
                      <v-avatar class="ml-n3" size="30">
                        <img src="https://cdn.vuetifyjs.com/images/lists/4.jpg" alt="John">
                      </v-avatar>
                      <v-avatar class="ml-n3" size="30">
                        <img src="https://cdn.vuetifyjs.com/images/lists/2.jpg" alt="John">
                      </v-avatar>
                      <v-avatar class="ml-n3" color="black" size="30">
                        <span class="caption white--text">+1</span>
                      </v-avatar>
                    </div>



                    <v-row align="center" justify="end">

                      <v-btn outlined class="blog-post-learn-btn" @click="openLink(post.link)">
                        <v-icon left class="blog-post-learn-icon">mdi-download</v-icon>
                        Download
                      </v-btn>

                    </v-row>
                  </v-list-item>
                </v-card-actions>
              </v-card>
            </v-col>
            <v-col cols="12" sm="4">
              <v-card elevation="10" class="rounded-xl ml-4" color="grey lighten-3" flat>
                <v-img src="../assets/terraform.png" height="140px"></v-img>
                <v-card-title>
                  <span class="text-h6 font-weight-light">Prototyping</span>
                </v-card-title>

                <v-card-text class="">
                  Explanation about module Explanation about module Explanation about module Explanation about module
                  Explanation about module Explanation about module
                </v-card-text>

                <v-card-actions class="mt-n7">
                  <v-list-item class="">
                    <div color="grey darken-3">

                      <v-avatar class="ml-n3" size="30">
                        <img src="https://cdn.vuetifyjs.com/images/lists/1.jpg" alt="John">
                      </v-avatar>
                      <v-avatar class="ml-n3" size="30">
                        <img src="https://cdn.vuetifyjs.com/images/lists/3.jpg" alt="John">
                      </v-avatar>
                      <v-avatar class="ml-n3" size="30">
                        <img src="https://cdn.vuetifyjs.com/images/lists/4.jpg" alt="John">
                      </v-avatar>
                      <v-avatar class="ml-n3" size="30">
                        <img src="https://cdn.vuetifyjs.com/images/lists/2.jpg" alt="John">
                      </v-avatar>
                      <v-avatar class="ml-n3" color="black" size="30">
                        <span class="caption white--text">+1</span>
                      </v-avatar>
                    </div>



                    <v-row align="center" justify="end">

                      <v-btn outlined class="blog-post-learn-btn" @click="openLink(post.link)">
                        <v-icon left class="blog-post-learn-icon">mdi-download</v-icon>
                        Download
                      </v-btn>

                    </v-row>
                  </v-list-item>
                </v-card-actions>
              </v-card>
            </v-col>
            <v-col cols="12" sm="4">
              <v-card elevation="10" class="rounded-xl ml-4" color="grey lighten-3" flat>
                <v-img src="../assets/terraform.png" height="140px"></v-img>
                <v-card-title>
                  <span class="text-h6 font-weight-light">Prototyping</span>
                </v-card-title>

                <v-card-text class="">
                  Explanation about module Explanation about module Explanation about module Explanation about module
                  Explanation about module Explanation about module
                </v-card-text>

                <v-card-actions class="mt-n7">
                  <v-list-item class="">
                    <div color="grey darken-3">

                      <v-avatar class="ml-n3" size="30">
                        <img src="https://cdn.vuetifyjs.com/images/lists/1.jpg" alt="John">
                      </v-avatar>
                      <v-avatar class="ml-n3" size="30">
                        <img src="https://cdn.vuetifyjs.com/images/lists/3.jpg" alt="John">
                      </v-avatar>
                      <v-avatar class="ml-n3" size="30">
                        <img src="https://cdn.vuetifyjs.com/images/lists/4.jpg" alt="John">
                      </v-avatar>
                      <v-avatar class="ml-n3" size="30">
                        <img src="https://cdn.vuetifyjs.com/images/lists/2.jpg" alt="John">
                      </v-avatar>
                      <v-avatar class="ml-n3" color="black" size="30">
                        <span class="caption white--text">+1</span>
                      </v-avatar>
                    </div>



                    <v-row align="center" justify="end">

                      <v-btn outlined class="blog-post-learn-btn" @click="openLink(post.link)">
                        <v-icon left class="blog-post-learn-icon">mdi-download</v-icon>
                        Download
                      </v-btn>

                    </v-row>
                  </v-list-item>
                </v-card-actions>
              </v-card>
            </v-col>
            <v-col cols="12" sm="4">
              <v-card elevation="10" class="rounded-xl ml-4" color="grey lighten-3" flat>
                <v-img src="../assets/terraform.png" height="140px"></v-img>
                <v-card-title>
                  <span class="text-h6 font-weight-light">Prototyping</span>
                </v-card-title>

                <v-card-text class="">
                  Explanation about module Explanation about module Explanation about module Explanation about module
                  Explanation about module Explanation about module
                </v-card-text>

                <v-card-actions class="mt-n7">
                  <v-list-item class="">
                    <div color="grey darken-3">

                      <v-avatar class="ml-n3" size="30">
                        <img src="https://cdn.vuetifyjs.com/images/lists/1.jpg" alt="John">
                      </v-avatar>
                      <v-avatar class="ml-n3" size="30">
                        <img src="https://cdn.vuetifyjs.com/images/lists/3.jpg" alt="John">
                      </v-avatar>
                      <v-avatar class="ml-n3" size="30">
                        <img src="https://cdn.vuetifyjs.com/images/lists/4.jpg" alt="John">
                      </v-avatar>
                      <v-avatar class="ml-n3" size="30">
                        <img src="https://cdn.vuetifyjs.com/images/lists/2.jpg" alt="John">
                      </v-avatar>
                      <v-avatar class="ml-n3" color="black" size="30">
                        <span class="caption white--text">+1</span>
                      </v-avatar>
                    </div>



                    <v-row align="center" justify="end">

                      <v-btn outlined class="blog-post-learn-btn" @click="openLink(post.link)">
                        <v-icon left class="blog-post-learn-icon">mdi-download</v-icon>
                        Download
                      </v-btn>

                    </v-row>
                  </v-list-item>
                </v-card-actions>
              </v-card>
            </v-col>
            <v-col cols="12" sm="4">
              <v-card elevation="10" class="rounded-xl ml-4" color="grey lighten-3" flat>
                <v-img src="../assets/terraform.png" height="140px"></v-img>
                <v-card-title>
                  <span class="text-h6 font-weight-light">Prototyping</span>
                </v-card-title>

                <v-card-text class="">
                  Explanation about module Explanation about module Explanation about module Explanation about module
                  Explanation about module Explanation about module
                </v-card-text>

                <v-card-actions class="mt-n7">
                  <v-list-item class="">
                    <div color="grey darken-3">

                      <v-avatar class="ml-n3" size="30">
                        <img src="https://cdn.vuetifyjs.com/images/lists/1.jpg" alt="John">
                      </v-avatar>
                      <v-avatar class="ml-n3" size="30">
                        <img src="https://cdn.vuetifyjs.com/images/lists/3.jpg" alt="John">
                      </v-avatar>
                      <v-avatar class="ml-n3" size="30">
                        <img src="https://cdn.vuetifyjs.com/images/lists/4.jpg" alt="John">
                      </v-avatar>
                      <v-avatar class="ml-n3" size="30">
                        <img src="https://cdn.vuetifyjs.com/images/lists/2.jpg" alt="John">
                      </v-avatar>
                      <v-avatar class="ml-n3" color="black" size="30">
                        <span class="caption white--text">+1</span>
                      </v-avatar>
                    </div>



                    <v-row align="center" justify="end">

                      <v-btn outlined class="blog-post-learn-btn" @click="openLink(post.link)">
                        <v-icon left class="blog-post-learn-icon">mdi-download</v-icon>
                        Download
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
import SideBar from '../components/SideBar'

export default {
  name: 'Home',

  components: {
    SideBar,
  },
}
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
