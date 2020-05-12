<template>
  <v-row justify="center">
    <v-dialog v-model="dialog" scrollable>
      <template v-slot:activator="{ on }">
        <v-icon :x-large="true" class="rotating" v-on="on">mdi-cog-outline</v-icon>
      </template>
      <v-card>
        <v-card-title>Выберите категорию</v-card-title>
        <v-divider></v-divider>
        <v-treeview :items="items"></v-treeview>
        <v-divider></v-divider>
        <v-card-actions>
          <v-btn color="blue darken-1" text @click="dialog = false">Сохранить</v-btn>
          <v-btn color="blue darken-1" text @click="dialog = false">Закрыть</v-btn>
        </v-card-actions>
      </v-card>
    </v-dialog>
  </v-row>
</template>

<script>
export default {
  props: [
    'items'
  ],
  data () {
    return {
      dialogm1: '',
      dialog: false
    }
  }
}
</script>
<style scoped>
  .v-treeview-node__root {
    min-height: 0px !important;
  }
  .v-treeview-node__level {
    width: 15px !important;
  }
</style>
