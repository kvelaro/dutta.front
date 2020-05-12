<template>
  <div>
      <v-app-bar
        color="#ddd"
        dense
      >
        <v-toolbar-title>Название ресурса</v-toolbar-title>
        <v-spacer></v-spacer>
        <div class="my-2">
          <v-btn text small>Воронеж</v-btn>
        </div>
        <v-menu
          left
          bottom
        >
          <template v-slot:activator="{ on }">
            <v-btn icon v-on="on">
              <v-icon>mdi-dots-vertical</v-icon>
            </v-btn>
          </template>
          <v-list>
            <v-list-item>
              <v-list-item-title>Вход</v-list-item-title>
            </v-list-item>
            <v-list-item>
              <v-list-item-title>Регистрация</v-list-item-title>
            </v-list-item>
          </v-list>
        </v-menu>
      </v-app-bar>
      <div class="caterories-select-gear">
        <categories-dialog :items="items"></categories-dialog>
      </div>
      <v-row justify="center">
        <v-col md="10" sm="9" xs="12">
          <v-container
            fluid
          >
            <v-row>
              <v-col md="8">
                <v-text-field>
                  <template v-slot:label>
                    <v-icon>mdi-magnify</v-icon>
                  </template>
                </v-text-field>
              </v-col>
              <v-col md="4">
                <v-select
                  v-model="metro"
                  :items="metroItems"
                  attach
                  chips
                  single-line="true"
                  label="Метро"
                  multiple
                  class="metro-select"
                ></v-select>
              </v-col>
            </v-row>
            <v-row>
              <v-col cols="3">
                <v-card class="good-item-card">
                  <v-container class="good-properties">
                    <span class="good-property-chip quick">срочно</span>
                    <span class="good-property-chip quality">качество</span>
                    <span class="good-property-chip quantity">количество</span>
                    <span class="good-property-chip profit">выгодно</span>
                    <span class="good-property-chip sponsored">реклама</span>
                  </v-container>
                  <v-container class="good-actions">
                    <v-icon>mdi-star-outline</v-icon>
                  </v-container>
                  <v-img
                    src="https://picsum.photos/350/165?random"
                    height="200"
                    class="grey darken-4"
                  ></v-img>
                  <v-card-title class="title">T-shirt</v-card-title>
                  <v-card-subtitle>50₽</v-card-subtitle>
                  <v-card-text>Москва, сегодня 22:05</v-card-text>
                </v-card>
              </v-col>
              <v-col cols="3">
                <v-card class="good-item-card">
                  <v-img
                    src="https://picsum.photos/350/165?random"
                    height="200"
                    class="grey darken-4"
                  ></v-img>
                  <v-card-title class="title">T-shirt</v-card-title>
                  <v-card-subtitle>50₽</v-card-subtitle>
                  <v-card-text>Москва, сегодня 22:05</v-card-text>
                </v-card>
              </v-col>
              <v-col cols="3">
                <v-card class="good-item-card">
                  <v-img
                    src="https://picsum.photos/350/165?random"
                    height="200"
                    class="grey darken-4"
                  ></v-img>
                  <v-card-title class="title">T-shirt</v-card-title>
                  <v-card-subtitle>50₽</v-card-subtitle>
                  <v-card-text>Москва, сегодня 22:05</v-card-text>
                </v-card>
              </v-col>
              <v-col cols="3">
                <v-card class="good-item-card">
                  <v-img
                    src="https://picsum.photos/350/165?random"
                    height="200"
                    class="grey darken-4"
                  ></v-img>
                  <v-card-title class="title">T-shirt</v-card-title>
                  <v-card-subtitle>50₽</v-card-subtitle>
                  <v-card-text>Москва, сегодня 22:05</v-card-text>
                </v-card>
              </v-col>
            </v-row>
          </v-container>
        </v-col>
      </v-row>
  </div>
</template>
<script>
import CategoriesDialog from './dialogs/Categories'
export default {
  components: {
    CategoriesDialog
  },
  data: () => ({
    metro: null,
    metroItems: ['Арбатская', 'Калужская', 'Львовская', 'Ново-Покровская'],
    imgs: [
      {
        src: 'https://picsum.photos/350/165?random'
      }
    ],
    items: [
      {
        id: 1,
        name: 'Applications :',
        children: [
          { id: 2, name: 'Calendar : app' },
          { id: 3, name: 'Chrome : app' },
          { id: 4, name: 'Webstorm : app' }
        ]
      },
      {
        id: 5,
        name: 'Documents :',
        children: [
          {
            id: 6,
            name: 'vuetify :',
            children: [
              {
                id: 7,
                name: 'src :',
                children: [
                  { id: 8, name: 'index : ts' },
                  { id: 9, name: 'bootstrap : ts' }
                ]
              }
            ]
          },
          {
            id: 10,
            name: 'material2 :',
            children: [
              {
                id: 11,
                name: 'src :',
                children: [
                  { id: 12, name: 'v-btn : ts' },
                  { id: 13, name: 'v-card : ts' },
                  { id: 14, name: 'v-window : ts' }
                ]
              }
            ]
          }
        ]
      },
      {
        id: 15,
        name: 'Downloads :',
        children: [
          { id: 16, name: 'October : pdf' },
          { id: 17, name: 'November : pdf' },
          { id: 18, name: 'Tutorial : html' }
        ]
      },
      {
        id: 19,
        name: 'Videos :',
        children: [
          {
            id: 20,
            name: 'Tutorials :',
            children: [
              { id: 21, name: 'Basic layouts : mp4' },
              { id: 22, name: 'Advanced techniques : mp4' },
              { id: 23, name: 'All about app : dir' }
            ]
          },
          { id: 24, name: 'Intro : mov' },
          { id: 25, name: 'Conference introduction : avi' }
        ]
      }
    ]
  })
}
</script>

<style>
  .metro-select.v-select.v-select--chips .v-select__selections {
    /* min-height: 0 !important; */
  }
  .v-chip.v-size--default {
    /* height: 20px !important; */
  }
  .v-select__selections {
    /* overflow: hidden !important; */
  }
  .good-item-card {
    opacity: 1;
  }
  .good-properties {
    position: absolute;
    z-index: 3;
    margin: 0 !important;
    padding: 0 !important;
  }
  .good-property-chip {
    display: table;
    color: #fff;
    padding: 5px;
    border-top-right-radius: 5px;
    border-bottom-right-radius: 5px;
    font-size: 10px;
    margin-top: 5px;
  }
  .quick {
    background-color: #a80a06;
  }
  .quantity {
    background-color: #cbc214;
  }
  .quality {
    background-color: #19a806;
  }
  .profit {
    background-color: #3597b4;
  }
  .sponsored {
    background-color: #564497;
  }
  .good-actions {
    position: absolute !important;
    right: 0 !important;
  }
  .good-actions i {
    position: absolute !important;
    right: 10px !important;
    z-index: 3;
    background: #ddd;
    border-radius: 100%;
    cursor: pointer;
  }
  .caterories-select-gear {
    position: absolute !important;
    top: 13%;
    left: 15px;
    cursor: pointer;
  }
  @-webkit-keyframes rotating /* Safari and Chrome */ {
  from {
    -webkit-transform: rotate(0deg);
    -o-transform: rotate(0deg);
    transform: rotate(0deg);
  }
  to {
    -webkit-transform: rotate(360deg);
    -o-transform: rotate(360deg);
    transform: rotate(360deg);
  }
}
@keyframes rotating {
  from {
    -ms-transform: rotate(0deg);
    -moz-transform: rotate(0deg);
    -webkit-transform: rotate(0deg);
    -o-transform: rotate(0deg);
    transform: rotate(0deg);
  }
  to {
    -ms-transform: rotate(360deg);
    -moz-transform: rotate(360deg);
    -webkit-transform: rotate(360deg);
    -o-transform: rotate(360deg);
    transform: rotate(360deg);
  }
}
.rotating {
  -webkit-animation: rotating 20s linear infinite;
  -moz-animation: rotating 20s linear infinite;
  -ms-animation: rotating 20s linear infinite;
  -o-animation: rotating 20s linear infinite;
  animation: rotating 20s linear infinite;
}
</style>
