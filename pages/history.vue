<template>
  <div>
    <v-timeline>
      <v-timeline-item
        v-for="item in historyData"
        :key="item.date"
      >
        <v-card>
          <v-card-subtitle>
            {{ item.date }}
          </v-card-subtitle>
          <v-card-text>
            <div
              v-for="event in item.topic"
              :key="event.summary"
            >
              {{ event.text }}<br>
              {{ event.summary }}
            </div>
          </v-card-text>
        </v-card>
      </v-timeline-item>
    </v-timeline>
  </div>
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
