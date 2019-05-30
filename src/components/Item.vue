<template>
  <v-flex md2 sm2 class="mr-2">
    <v-card class="item-specific">
      <v-card-title><h3>New Item</h3></v-card-title>
      <v-card-text>
        <h3 class="text-body">
          <slot></slot>
        </h3>
      </v-card-text>
    </v-card>
  </v-flex>
</template>

<script>
  export default {
  }
</script>

<style scoped>
.item-specific {
  background-color: bisque;
  color: black;
}
.item-specific:hover {
  background-color: lightblue;
  color: yellow;
}
.text-body {
  text-align: center
}
</style>
