<template>
  <v-container>
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
    <special-cards />
    <v-divider />
    <reactions :reactions="reactionsData" />
  </v-container>
</template>

<script lang="ts">
import Vue from 'vue'
import SpecialCards from '@/components/SpecialCards.vue'
import Reactions from '@/components/Reactions.vue'

export default Vue.extend({
  components: {
    SpecialCards,
    Reactions
  },
  computed: {
    reactionsData: () => require('@/assets/reactions.json').index
  }
})
</script>
