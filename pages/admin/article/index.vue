<template>
  <v-container>
    <v-row>
      <v-col cols="8">
        <h1 class="font-weight-bold">Artikel</h1>
      </v-col>
      <v-col cols="4">
        <v-btn to="/admin/article/create" rounded large flat color="success">
          <v-icon>fa fa-plus</v-icon>
          Buat Postingan
        </v-btn>
      </v-col>
    </v-row>
    <v-row>
      <v-data-table
      :headers="headers"
      ></v-data-table>
    </v-row>
  </v-container>
</template>
<script>
export default {
  layout: "admin",
  data: () => ({
    headers: [
      {text: "Judul",value: "name",},
      { text: "category", value: "calories" },
      { text: "Thumbnail", value: "fat" },
      { text: "Status", value: "carbs" },
      { text: "Tanggal Publikasi", value: "protein" },
      { text: "Tanggal Dibuat", value: "iron" },
      { text: "Aksi",sortable: false,}
    ],
  }),
};
</script>