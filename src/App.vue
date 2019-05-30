<template>
  <v-app>
    <v-toolbar app>
      <v-toolbar-title class="headline text-uppercase">
        <span>Vuetify</span>
        <span class="font-weight-light">MATERIAL DESIGN</span>
      </v-toolbar-title>
      <v-spacer></v-spacer>
      <v-btn
        flat
        href="https://github.com/vuetifyjs/vuetify/releases/latest"
        target="_blank"
      >
        <span class="mr-2">Latest Release</span>
      </v-btn>
    </v-toolbar>

    <v-content>
      <v-layout row wrap>
        <v-flex xs12 md12 sm12>
          <new-item @createNewItem="addItem($event)" :totalItem="items.length" :itemLimit="itemLimit"></new-item>
        </v-flex>
        <v-flex xs12 md12 sm12>
          <item-layout :items="items" @deletedItem="deletedItem($event)"/>
        </v-flex>
      </v-layout>
    </v-content>
  </v-app>
</template>

<script>
import ItemLayout from './components/ItemLayout'
import NewItem from './components/NewItem'

export default {
  name: 'App',
  components: {
    ItemLayout,
    NewItem
  },
  data() {
    return {
      items: [
      ],
      itemLimit: 10,
    }
  },

  methods: {
    addItem(addedItem) {
      if(this.items.includes(addedItem)) {
        alert("please enter other name")
        return false
      }
      if(this.items.length > this.itemLimit) {
        alert("please remove item")
        return false
      }
      this.items.push(addedItem)
    },
    deletedItem(index) {
      this.items.splice(index, 1)
    },
  }
}
</script>
