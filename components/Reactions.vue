<template>
  <v-container fluid>
    <div>
      <div class="text-h3 text-center mb-2">
        周囲の反応
      </div>
      <div class="text-body-1 text-center">
        奇跡の世代の活動は様々な場所で反響を呼び、その都度高い評価をいただいております。
        その反応の一部を掲載させていただきます。
      </div>
    </div>
    <v-row>
      <reaction-item
        v-for="item in reactions"
        :key="item.name"
        :name="item.name"
        :description="item.description"
      />
    </v-row>
  </v-container>
</template>

<script lang="ts">
import Vue from 'vue'
import ReactionItem from '@/components/ReactionItem.vue'
const d : reactionData = require('@/assets/reactions.json')

interface Reaction {
  name: string,
  description: string
}

interface reactionData {
  [key: string]: Array<Reaction>
}

export default Vue.extend({
  components: {
    'reaction-item': ReactionItem
  },
  data () {
    return {
      reactions: d[1]
    }
  }
})
</script>
