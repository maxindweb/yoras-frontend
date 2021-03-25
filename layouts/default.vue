<template>
  <v-app>
    <v-app-bar app color="#4B47FF">
      <v-img src="logo.png" max-height="50" max-width="50"></v-img>
      <v-container>
        <v-app-bar-title>
          <h4>Paroki St.Yohanes Rasul</h4>
          <h5>Pringwulung</h5>
        </v-app-bar-title>
      </v-container>

      <v-spacer></v-spacer>
      <v-btn text nuxt to="/">Beranda</v-btn>
      <v-btn text nuxt to="/news">Berita</v-btn>
      <v-btn text nuxt to="/renungan">Renungan</v-btn>
      <v-menu offset-y>
        <template v-slot:activator="{ on, attrs }">
          <v-btn text v-bind="attrs" v-on="on"> Informasi </v-btn>
        </template>
        <v-list>
          <v-list-item v-for="(item, index) in items" :key="index">
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item>
        </v-list>
      </v-menu>
      <v-menu offset-y>
        <template v-slot:activator="{ on, attrs }">
          <v-btn text v-bind="attrs" v-on="on"> Tentang Kami </v-btn>
        </template>
        <v-list>
          <v-list-item v-for="(item, index) in items" :key="index">
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item>
        </v-list>
      </v-menu>
    </v-app-bar>
    <v-main>
      <nuxt-child></nuxt-child>
    </v-main>
    <v-footer dark padless>
      <v-card class="flex" flat tile>
        <v-row no-gutters>
          <v-col cols="4">
            <v-card-title>Paroki St.Yohanes Rasul Pringwulung</v-card-title>
            <v-col style="padding-top: -50px" cols="8">
              <v-card-text class="text-center font">
                Sarana berbagi informasi dan penghayatan iman umat Paroki St.
                Yohanes Rasul Pringwulung, Yogyakarta.
              </v-card-text>
            </v-col>
          </v-col>
          <v-col cols="2">
            <v-card-title> Link terkait </v-card-title>
          </v-col>
          <v-col cols="3">
            <v-card-title> Hubungi Kami </v-card-title>
          </v-col>
          <v-col cols="2">
            <v-card-title> Social Media </v-card-title>
          </v-col>
        </v-row>
      </v-card>
      <v-card-text class="text-center">
        Design System By Team IT Yoras Pringwulung
      </v-card-text>
      <v-card-text class="text-center">
        &copy; {{ new Date().getFullYear() }} —
        <strong>Paroki St.Yohanes Rasul Pringwulung</strong>
      </v-card-text>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  data() {
    return {
      clipped: false,
      drawer: false,
      fixed: false,
      items: [
        {
          icon: "mdi-apps",
          title: "Welcome",
          to: "/",
        },
        {
          icon: "mdi-chart-bubble",
          title: "Inspire",
          to: "/inspire",
        },
      ],
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: "Vuetify.js",
    };
  },
};
</script>
