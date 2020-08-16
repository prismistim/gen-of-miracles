<template>
  <v-row justify="center">
    <v-col
      v-for="item in items"
      :key="item.title"
      cols="12"
      lg="4"
      md="6"
      sm="12"
      xs="12"
    >
      <v-card
        :href="item.url"
        target="_blank"
        height="120"
        color="green"
        hover
      >
        <v-card-title>{{ item.title }}</v-card-title>
        <v-card-text>{{ item.description }}</v-card-text>
      </v-card>
    </v-col>
  </v-row>
</template>

<script lang="ts">
import Vue from 'vue'

interface Items {
  title: string,
  description: string,
  url: string
}

interface Data {
  items: Array<Items>
}

export default Vue.extend({
  data (): Data {
    return {
      items: [
        {
          title: '動画ができない動画',
          description: '我々は日々の生活をより良いものにするため、何気ない日常を奇跡へと変えて見せます。',
          url: 'https://www.youtube.com/watch?v=gvEtamZG-TM'
        },
        {
          title: 'クイズ「奇跡の難問」',
          description: '全問正解で今日から君も奇跡の世代だ！',
          url: 'https://forms.office.com/Pages/ResponsePage.aspx?id=-lLnVMi5xU6ar1zvlrJNZD9_N8jlge9Pr_F7uCakjqtUNUNYVDMxTTdNTTRFUERQM0dCVTU5ODJRVC4u'
        }
      ]
    }
  }
})
</script>
