<template>
  <v-container>
    <div class="text-h3 ma-2">
      SOMA
    </div>
    <div class="text-subtitle-1 ma-2">
      奇跡の世代の名付け親
    </div>
    <v-list>
      <v-list-item>
        <v-list-item-content>hoge</v-list-item-content>
      </v-list-item>
    </v-list>
    <div class="text-h4 ma-2">
      Private Photos
    </div>
    <ImageGrids :name="name" />
    <v-row justify="center">
      <v-col cols="12">
        <div>
          <v-img
            src="/images/members/soma/logo.gif"
            width="300"
          />
        </div>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
import ImageGrids from '@/components/ImageGrids.vue'

export default {
  components: {
    ImageGrids
  },
  data () {
    return {
      name: 'soma'
    }
  }
}
</script>
