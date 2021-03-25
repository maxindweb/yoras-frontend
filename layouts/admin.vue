<template>
  <v-app>
    <v-app-bar app>
      <v-toolbar-title>Admin Yoras PW</v-toolbar-title>
    </v-app-bar>
    <v-navigation-drawer
      app
      v-model="drawer"
      :mini-variant.sync="mini"
      permanent
    >
      <v-list-item class="px-2">
        <v-list-item-avatar>
          <v-img src="https://randomuser.me/api/portraits/men/85.jpg"></v-img>
        </v-list-item-avatar>

        <v-list-item-title>John Leider</v-list-item-title>

        <v-btn icon @click.stop="mini = !mini">
          <v-icon>fa fa-chevron-left </v-icon>
        </v-btn>
      </v-list-item>

      <v-divider></v-divider>

      <v-list dense>
        <v-list-item
          v-for="item in items"
          :key="item.title"
          link
          nuxt
          :to="item.link"
        >
          <v-list-item-icon>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-icon>

          <v-list-item-content>
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
        <v-list-item >
          <v-list-item-icon>
            <v-icon>fa fa-sign-out</v-icon>
          </v-list-item-icon>

          <v-list-item-content>
            <v-list-item-title>Logout</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <v-main>
      <nuxt-child></nuxt-child>
    </v-main>
  </v-app>
</template>
<script>
export default {
  data() {
    return {
      drawer: true,
      items: [
        {
          title: "Home",
          icon: "fa fa-home",
          link: "/admin/home",
        },
        {
          title: "artikel",
          icon: "fa fa-file-text",
          link: "/admin/article",
        },
        {
          title: "category",
          icon: "fa fa-file-text-o",
          link: 'category'
        },
        {
          title: "galery",
          icon: "fa fa-file-image-o",
        },
        { title: "Users", icon: "fa fa-users", link: "/admin/users" },
      ],
      mini: true,
    };
  },
};
</script>
