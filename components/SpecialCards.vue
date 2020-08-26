<template>
  <div>
    <v-row>
      <v-col cols="12">
        <div class="text-h3">
          Special
        </div>
      </v-col>
    </v-row>
    <v-row justify="center">
      <SpecialCardItem
        v-for="item in items"
        :key="item.title"
        :url="item.url"
        :title="item.title"
        :description="item.description"
      />
    </v-row>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import SpecialCardItem from '@/components/SpecialCardItem.vue'

interface Items {
  title: string,
  description: string,
  url: string
}

interface Data {
  items: Array<Items>
}

export default Vue.extend({
  components: {
    SpecialCardItem
  },
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
