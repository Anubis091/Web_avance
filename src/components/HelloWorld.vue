<template>
<v-form v-model="valid">
    <v-container>
      <v-row>
        <v-col
          cols="12"
          md="4"
        >
          <v-text-field
            v-model="name"
            label="Name"
            required
          ></v-text-field>
        </v-col>

        <v-col
          cols="12"
          md="4"
        >
          <v-text-field
            v-model="description"
            label="Description"
            required
          ></v-text-field>
        </v-col>
       <v-btn v-on:click="AjouterElement">Ajouter</v-btn>

        <v-col
          cols="12"
          md="4"
        >
        </v-col>

      </v-row>
      <v-card max-width="1500" class="mx-auto" v-for="(item, index) in table" v-bind:key="item.id" >
    <v-card-title>{{item.name}}</v-card-title>
    <v-card-text>{{item.description}}</v-card-text>
    <v-card-actions>
      <v-btn v-on:click="SupprimerElement(index)">Supprimer</v-btn>
    </v-card-actions>

      </v-card>
    </v-container>
  </v-form>
  </template>
<script>
export default {
  data: () => ({
    table: [],
    valid: false,
    name: '',
    description: ''
  }),
  methods: {
    AjouterElement: function () {
      this.table.push({ name: this.name, description: this.description })
    },
    SupprimerElement: function (index) {
      this.table.splice(index, 1)
    }
  }
}
</script>
