<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <ItemLayout msg="Welcome to Your Vue.js + TypeScript App"/>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
import ItemLayout from '@/components/ItemLayout.vue'; // @ is an alias to /src

@Component({
  components: {
    ItemLayout,
  },
})
export default class Home extends Vue {}
</script>
