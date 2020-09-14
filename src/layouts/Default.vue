<template>
  <v-app class="app">
    <v-navigation-drawer app>
       <v-list v-for="item in menuItems" :key="item.title">
      <v-list-item class="pl-lg-5" :to="$url(item.url)">
        <v-list-item-icon>
          <v-icon>
            {{ item.icon }}
          </v-icon>
        </v-list-item-icon>
        <v-list-item-content>
          <v-list-item-title>
            {{ item.title }}
          </v-list-item-title>
        </v-list-item-content>
      </v-list-item>
    </v-list>
    </v-navigation-drawer>

    <v-main>
      <slot />
    </v-main>
  </v-app>
</template>

<script>
export default {
  data () {
    return {
       menuItems: [
        {
          title: 'Home',
          url: '/',
          icon: 'mdi-home'
        },
        {
          title: 'Articles',
          url: '/articles',
          icon: 'mdi-book-open-outline'
        },
      ]
    }
  }
}
</script>
