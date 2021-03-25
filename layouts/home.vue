<template>
  <v-app>
    <div>
      <v-app-bar
        app
        dark
        height="500"
        shrink-on-scroll
        src="altar.jpeg"
        fade-img-on-scroll
        color="#4B47FF"
      >
        <template v-slot:img="{ props }">
          <v-img
          position="center center"
            v-bind="props"
            gradient="to top right, rgba(0,0,0,0), rgba(1,1,2,2)"
          ></v-img>
        </template>
        <v-img src="logo.png" max-height="50" max-width="50"></v-img>
        <v-app-bar-title style="color: white"> Paroki Pringwulung</v-app-bar-title>
        <v-spacer></v-spacer>
        <v-btn text nuxt to="/">Home</v-btn>
        <v-btn text nuxt to="/news">Berita</v-btn>
        <v-btn text nuxt to="/renungan">Renungan</v-btn>
        <v-menu offset-y>
          <template v-slot:activator="{ on, attrs }">
            <v-btn v-bind="attrs" v-on="on" text> informasi </v-btn>
          </template>
          <v-list>
            <v-list-item
            v-for="information in informations"
            :key="information.title"
            link
            nuxt
            >
              <v-list-item-title>{{information.title}}</v-list-item-title>
            </v-list-item>
          </v-list>
        </v-menu>
        <v-menu offset-y>
          <template v-slot:activator="{ on, attrs }">
            <v-btn v-bind="attrs" v-on="on" text> tentang kami </v-btn>
          </template>
          <v-list>
            <v-list-item
            v-for="about in abouts"
            :key="about.title "
            link
            nuxt
            :to="about.link"
            >
              <v-list-item-title> {{about.title}}</v-list-item-title>
            </v-list-item>
          </v-list>
        </v-menu>
      </v-app-bar>
    </div>
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
    return{
      informations: [
        {
          title: "kegiatan Paroki",
          link: "event"
        },
        {
          title: "Pelayanan"
        },
        {
          title: "Jadwal Misa"
        },
        {
          title: "Kalender Liturgi"
        }
      ],
      abouts: [
        {
          title: "Sejarah"
        },
        {
          title: "Pastor Paroki"
        },
        {
          title: "Dewan Paroki"
        },
        {
          title: "Lingkungan"
        }
      ]
    }
  }
};
</script>