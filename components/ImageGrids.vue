<template>
  <v-row class="mx-1">
    <v-col cols="12" sm="4">
      <v-card class="d-flex mb-2">
        <v-img :src="`/images/members/${name}/1.jpg`" />
      </v-card>
      <v-card >
        <v-img :src="`/images/members/${name}/2.jpg`" />
      </v-card>
    </v-col>
    <v-col cols="12" sm="4">
      <v-card>
        <v-img :src="`/images/members/${name}/3.jpg`" />
      </v-card>
    </v-col>
    <v-col cols="12" sm="4">
      <v-card class="mb-2">
        <v-img :src="`/images/members/${name}/4.jpg`" />
      </v-card>
      <v-card>
        <v-img :src="`/images/members/${name}/5.jpg`" />
      </v-card>
    </v-col>
  </v-row>
</template>

<script>
export default {
  props: {
    name: {
      type: String,
      default: null
    }
  }
}
</script>
