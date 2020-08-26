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
        <v-list-group
          prepend-icon="mdi-account-multiple"
          no-action
        >
          <template v-slot:activator>
            <v-list-item-title>Member</v-list-item-title>
          </template>
          <v-list-item
            v-for="(member, i) in members"
            :key="i"
            :to="member.to"
            router
            exact
          >
            <v-list-item-content>
              <v-list-item-title v-text="member.name" />
            </v-list-item-content>
          </v-list-item>
        </v-list-group>
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
      <nuxt />
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
      is_darked: false,
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
          icon: 'mdi-history',
          title: 'History',
          to: '/history'
        }
      ],
      members: [
        {
          name: 'SOMA',
          to: '/member/soma'
        },
        {
          name: 'TNK',
          to: '/member/tnk'
        },
        {
          name: 'MizukiCom',
          to: '/member/mizukicom'
        },
        {
          name: 'Wakame-Chan',
          to: '/member/wakame'
        }
      ],
      miniVariant: false,
      title: '奇跡の世代'
    }
  },
  mounted () {
    this.is_darked = window.matchMedia('(prefers-color-scheme: dark)').matches
    this.$vuetify.theme.dark = this.is_darked
  }
}
</script>
