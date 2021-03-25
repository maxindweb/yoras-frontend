<template>
  <v-container>
    <v-row>
      <h1>Berita</h1>
    </v-row>
    <v-row>
      <v-card>
        <v-row>
          <v-col cols="3">
            <v-img position="center center" src="altar.jpeg" max-width="280" max-height="330"></v-img>
          </v-col>
          <v-col cols="8">
            <v-row>
              <v-card-title>Judul Artikel</v-card-title>
            </v-row>
            <v-row>
              <v-col class="12">
                <v-card-text class="text-justify" nuxt>
                  Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed
                  do eiusmod tempor incididunt ut labore et dolore magna aliqua.
                  Ut enim ad minim veniam, quis nostrud exercitation ullamco
                  laboris nisi ut aliquip ex ea commodo consequat. Duis aute
                  irure dolor in reprehenderit in voluptate velit esse cillum
                  dolore eu fugiat nulla pariatur.Excepteur sint occaecat
                  cupidatat non proident, sunt in culpa qui officia deserunt
                  mollit anim id est laborum.Baca Selengkapnya
                </v-card-text>
              </v-col>
            </v-row>
          </v-col>
        </v-row>
      </v-card>
    </v-row>
  </v-container>
</template>