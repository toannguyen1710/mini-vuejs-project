<template>
<v-layout class="pa-4" row wrap>
   <Item v-for="(item, index) in items" :key="item" @click.native="delItem(index)">{{item}}</Item>
</v-layout>
</template>

<script>
import Item from '../../src/components/Item'
export default {
  components: {
    Item
  },
  props: {
    items: {
      type: Array,
      default: []
    }
  },
  methods: {
    delItem(index) {
      this.$emit('deletedItem', index)
    }
  }
}
</script>


