<template>
  <v-container fluid>
    <v-row>
      <v-col sm="12">
        <v-card
          class="mx-auto mb-2"
          max-width="344"
        >
          <v-img
            src="/images/ours.png"
          />
        </v-card>
      </v-col>
    </v-row>
    <div class="mb-2">
      <div class="text-h2 text-center mb-2">
        Welcome to "奇跡の世代"
      </div>
      <div class="text-subtitle-1 text-center">
        今まで数々の奇跡を起こしてきた4人の戦士による特設サイトです
      </div>
    </div>
    <special-cards />
    <v-divider />
    <reactions :reactions="reactionsData" />
  </v-container>
</template>

<script>
import Vue from 'vue'
import SpecialCards from '@/components/SpecialCards.vue'
import Reactions from '@/components/Reactions.vue'
import reactionsDataJson from '@/assets/reactions.json'

export default Vue.extend({
  components: {
    SpecialCards,
    Reactions
  },
  computed: {
    reactionsData: () => reactionsDataJson.index
  }
})
</script>
