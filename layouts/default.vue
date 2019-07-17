<template>
  <v-app>
    <v-navigation-drawer
      v-model="drawer"
      style="background: linear-gradient(25deg, rgb(51, 8, 103), rgb(48, 207, 208));"
      dark
      fixed
      app
    >
      <v-list style="background: rgba(0, 0, 0, 0)">
        <v-list-tile
          v-for="(item, i) in items"
          :key="i"
          :to="item.to"
          router
          exact
        >
          <v-list-tile-action>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-tile-action>
          <v-list-tile-content>
            <v-list-tile-title v-text="item.title" />
          </v-list-tile-content>
        </v-list-tile>
      </v-list>
    </v-navigation-drawer>
    <v-toolbar
      v-if="!drawer"
      dark
      style="background: linear-gradient(25deg, rgb(51, 8, 103), rgb(48, 207, 208));"
      fixed
      app
    >
      <v-toolbar-title v-text="title" />
    </v-toolbar>
    <v-content>
      <v-container>
        <nuxt />
        <v-footer absolute fixed>
          <v-text-field
            class="mx-2"
            solo
            label="Outline"
            outline/>
        </v-footer>
      </v-container>
    </v-content>
  </v-app>
</template>

<script>
export default {
  data() {
    return {
      drawer: true,
      items: [
        {
          icon: 'apps',
          title: 'Welcome',
          to: '/'
        },
        {
          icon: 'bubble_chart',
          title: 'Inspire',
          to: '/inspire'
        }
      ],
      title: 'ToMe'
    }
  }
}
</script>
