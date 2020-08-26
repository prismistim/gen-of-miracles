<template>
  <v-col
    cols="12"
    lg="6"
    md="6"
    sm="12"
    xs="12"
  >
    <v-card
      :href="url"
      target="_blank"
      height="120"
      color="green"
      hover
    >
      <v-card-title>{{ title }}</v-card-title>
      <v-card-text>{{ description }}</v-card-text>
    </v-card>
  </v-col>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  props: {
    url: {
      type: String,
      default: null
    },
    title: {
      type: String,
      default: null
    },
    description: {
      type: String,
      default: null
    }
  }
})
</script>
