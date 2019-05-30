<template>
 <v-layout class="pa-4" row wrap>
   <v-flex sm12 md12>
     <v-form>
        <v-flex sm12 md12>
          <v-layout row>
              <v-flex class="mr-4" sm6 dm6>
                <v-textarea
                  v-model="item"
                  outline
                  name="input-7-4"
                  label="Outline textarea">
                </v-textarea>
              </v-flex>
              <v-flex sm6 md6>
                  <v-responsive class="block-square"
                    :style="{ background: `rgb(${red}, ${green}, ${blue})` }"
                    height="300px"
                  ></v-responsive>
              </v-flex>
          </v-layout>
        </v-flex>
        <v-flex sm12 md12>
          <v-layout row>
            <v-flex sm6 md6>
                <v-btn color="success" @click.prevent="addItem()">Add item</v-btn>
            </v-flex>
            <v-flex sm6 md6>
                <v-slider
                  v-model="red"
                  :max="itemLimit * 25"
                  label="R"
                ></v-slider>
            </v-flex>
          </v-layout>
        </v-flex>
     </v-form>
   </v-flex>
 </v-layout>
</template>

<script>
export default {
  props: {
    itemLimit: {
      type: Number,
      default: 0,
    },
    totalItem: {
      type: Number,
      default: 0,
    }
  },
  data() {
    return {
      item: '',
      red: 0,
      green: 0,
      blue: 0,
    }
  },
  watch: {
    totalItem(oldVal, newVal) {
      this.red = Math.round(oldVal / this.itemLimit * 255);
      this.green = this.red + 30;
      this.blue = this.green -30;
      console.log("oldvalue:" + oldVal + "," + "newval:" + newVal)
    }
  },
  methods: {
    addItem() {
      this.$emit('createNewItem', this.item)
      this.item = ''
    }
  }
}
</script>

<style scoped>
  .block-square {
    width: 300px;
    margin: auto;
  }
</style>
