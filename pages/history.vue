<template>
  <v-container>
    <v-row>
      <v-col cols="12">
        <div class="text-h3">
          History
        </div>
      </v-col>
      <v-col cols="12">
        奇跡の世代がこれまでに歩んできた歴史を紹介します。
      </v-col>
    </v-row>
    <v-timeline
      dense
    >
      <v-timeline-item
        v-for="item in historyData"
        :key="item.date"
      >
        <v-card>
          <v-card-subtitle>
            {{ item.date }}
          </v-card-subtitle>
          <v-card-text>
            <v-card
              v-for="event in item.topic"
              :key="event.summary"
              style="margin-bottom: 10px"
              outlined
            >
              <v-card-title>
                {{ event.summary }}
              </v-card-title>
              <v-card-text class="text--primary">
                <div>
                  {{ event.text }}
                </div>
              </v-card-text>
            </v-card>
          </v-card-text>
        </v-card>
      </v-timeline-item>
    </v-timeline>
  </v-container>
</template>

<script lang="ts">
import Vue from 'vue'
import historyDataJson from '@/assets/history.json'

interface Topic {
  summary: string,
  text: string
}

interface Event {
  date: string,
  topic: Array<Topic>
}

interface History {
  [key: string]: Array<Event>
}

export default Vue.extend({
  computed: {
    historyData: () => historyDataJson.history
  }
})
</script>
