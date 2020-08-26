<template>
  <v-container>
    <v-row>
      <v-col cols="12">
        <div class="text-h3">
          About
        </div>
      </v-col>
      <v-col cols="12">
        <div class="text-body-1">
          奇跡の世代とは、実験の天才たちの総称。国から支援金が出される
          ほど研究で有名な国立工科大学岐阜校において、1000人を超える
          生徒達の頂点に立ち、「10年に一人の天才」と呼ばれた4人の生徒達の
          ことである。同じ年、同じ学年、同じ学校に10年に一人の逸材が4人も
          集まったことから、「奇跡」と呼ばれる。
          彼らは一人一人が10年に一人の天才でありながらもそれぞれがオンリー
          ワンの才能を秘めており、そのセンスは他のプレイヤーでは全く
          太刀打ちできないほどであった。彼らの絆は一生続くと思われたが、
          Wakame-Chanが留年してしまったことにより、彼らが集まることは無く
          なってしまった。
        </div>
      </v-col>
    </v-row>
    <v-row>
      <OurTeams class="ma-2" />
    </v-row>
    <v-divider />
    <Reactions class="my-2" :reactions="reactionsData" />
  </v-container>
</template>

<script>
import Vue from 'vue'
import Reactions from '@/components/Reactions.vue'
import OurTeams from '@/components/OurTeams.vue'

export default Vue.extend({
  components: {
    Reactions,
    OurTeams
  },
  computed: {
    reactionsData: () => require('@/assets/reactions.json').about
  }
})
</script>
