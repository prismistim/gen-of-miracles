<template>
  <v-row>
    <OurTeamItem
      v-for="(item, i) in members"
      :key="i"
      :name="item.name"
      :job="item.job"
    />
  </v-row>
</template>

<script lang="ts">
import Vue from 'vue'
import OurTeamItem from '@/components/OurTeamItem.vue'

export default Vue.extend({
  components: {
    OurTeamItem
  },
  computed: {
    members: () => [
      {
        name: 'SOMA',
        job: 'Leader'
      },
      {
        name: 'TNK',
        job: 'Developer'
      },
      {
        name: 'MizukiCom',
        job: 'Designer'
      },
      {
        name: 'Wakame-Chan',
        job: 'Dubtter'
      }
    ]
  }
})
</script>
