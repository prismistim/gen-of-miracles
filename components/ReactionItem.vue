<template>
  <v-col
    cols="12"
    lg="6"
    md="6"
    sm="6"
  >
    <v-skeleton-loader
      :loading="loading"
      type="list-item-avatar-three-line"
    >
      <v-card min-height="120">
        <v-row>
          <v-col
            cols="12"
          >
            <div class="mb-2">
              <v-avatar class="ml-4">
                <img
                  :src="'/images/avatar/' + name + '.jpg'"
                >
              </v-avatar>
              <v-chip class="mx-2">
                {{ name }}
              </v-chip>
            </div>
            <div class="text-body-2 mx-4">
              {{ description }}
            </div>
          </v-col>
        </v-row>
      </v-card>
    </v-skeleton-loader>
  </v-col>
</template>

<script lang="ts">
import Vue from 'vue'

interface Data {
  loading: boolean
}

export default Vue.extend({
  props: {
    name: {
      type: String,
      default: ''
    },
    description: {
      type: String,
      default: ''
    }
  },
  data (): Data {
    return {
      loading: true
    }
  },
  mounted () {
    this.loading = false
  }
})
</script>
