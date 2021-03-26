<template>
  <v-container grid-list-lg fill-height>
    <v-layout row wrap justify-center align-content-center>
      <v-col cols="6">
        <v-card>
          <v-app-bar>
            <v-toolbar-title
              ><v-card-title class="text-center">
                Login</v-card-title
              ></v-toolbar-title
            >
          </v-app-bar>
          <v-form @submit.prevent="login">
            <v-card-text>
              <v-text-field
                label="Email"
                v-model="email"
                :rules="[rule.required]"
              ></v-text-field>
              <v-text-field
                label="Password"
                v-model="password"
                :rules="[rule.required]"
              ></v-text-field>
            </v-card-text>
            <v-card-text class="text-center">
              <v-btn
                color="success"
                :loading="loading"
                type="submit"
                rounded
                large
                block
                >Login</v-btn
              >
            </v-card-text>
          </v-form>
        </v-card>
      </v-col>
    </v-layout>
  </v-container>
</template>
<script>
export default {
  layout: "login",
  data: () => ({
    email: null,
    password: null,
    rule: {
      required: (v) => !!v || "Harus diisi",
    },
    loading: false,
  }),
  methods: {
    async login() {
      try {
        const res = await this.$auth.loginWith("local", {
          data: {
            email: this.email,
            password: this.password,
          },
        });
        console.log(res);
        this.$router.push('/admin/home')
      } catch (err) {
        console.log(err);
      }
    },
  },
};
</script>