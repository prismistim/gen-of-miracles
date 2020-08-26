<template>
  <v-col
    cols="6"
    md="3"
    sm="6"
  >
    <v-card>
      <v-img
        :src="'/images/ours/' + name.toLowerCase() + '.jpg'"
      />
      <v-card-title>
        {{ name }}
      </v-card-title>
      <v-card-subtitle>
        {{ job }}
      </v-card-subtitle>
    </v-card>
  </v-col>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  props: {
    name: {
      type: String,
      default: null
    },
    job: {
      type: String,
      default: null
    }
  }
})
</script>
