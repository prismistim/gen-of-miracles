<template>
  <v-app dark>
    <v-navigation-drawer
      v-model="drawer"
      :mini-variant="miniVariant"
      :clipped="clipped"
      fixed
      app
    >
      <v-list>
        <v-list-item
          v-for="(item, i) in items"
          :key="i"
          :to="item.to"
          router
          exact
        >
          <v-list-item-action>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title v-text="item.title" />
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <v-app-bar
      :clipped-left="clipped"
      fixed
      dense
      collapse
      collapse-on-scroll
      flat
      app
    >
      <v-app-bar-nav-icon @click.stop="drawer = !drawer" />
      <v-toolbar-title v-text="title" />
      <v-spacer />
      <v-btn
        icon
        href="https://github.com/prismistim/gen-of-miracles"
        target="_blank"
      >
        <v-icon>mdi-github</v-icon>
      </v-btn>
    </v-app-bar>
    <v-main>
      <v-container>
        <nuxt />
      </v-container>
    </v-main>
    <v-footer padless>
      <v-row
        align="center"
        justify="center"
      >
        <v-col cols="12">
          <v-img
            src="/images/footer.png"
            max-width="300px"
          />
        </v-col>
        <v-text>&copy; {{ new Date().getFullYear() }} gen-of-miracles</v-text>
      </v-row>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  data () {
    return {
      clipped: false,
      drawer: false,
      fixed: false,
      items: [
        {
          icon: 'mdi-home-variant',
          title: 'Home',
          to: '/'
        },
        {
          icon: 'mdi-information',
          title: 'About',
          to: '/about'
        },
        {
          icon: 'mdi-account-multiple',
          title: 'Member',
          to: '/member'
        },
        {
          icon: 'mdi-history',
          title: 'History',
          to: '/history'
        }
      ],
      miniVariant: false,
      title: '奇跡の世代'
    }
  }
}
</script>

<style>
/* @import url('https://fonts.googleapis.com/css2?family=Noto+Serif+JP:wght@400;600&display=swap');

.v-application {
  font-family: "Noto Serif JP", serif;
} */
</style>
