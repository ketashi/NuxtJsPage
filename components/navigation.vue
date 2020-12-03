<template>
  <div>
    <v-app-bar fixed dark class="navigation-opacity" elevate-on-scroll>
      <v-app-bar-nav-icon
        @click.stop="drawer = !drawer"
        class="navigation-show"
      ></v-app-bar-nav-icon>
      <v-toolbar-title>
        <nuxt-link to="/" class="text-white text-decoration-none"> Mangos SAC </nuxt-link>
      </v-toolbar-title>
      <v-spacer></v-spacer>
      <!-- show menu grid desktop -->
      <nuxt-link
        v-for="(item, id) in navigates"
        :key="id"
        :to="item.link"
        class="text-white text-decoration-none navigation-app"
        transition="slide-y-transition"
      >
        <v-btn text class="ma-2">
          {{ item.name }}
        </v-btn>
      </nuxt-link>
    </v-app-bar>

    <!-- hidden menu grid desktop -->
    <v-navigation-drawer v-model="drawer" fixed temporary>
      <v-list dense>
        <nuxt-link
          v-for="(item, id) in navigates"
          :key="id"
          :to="item.link"
          class="text-white text-decoration-none"
        >
          <v-list-item link>
            <v-list-item-content>
              <v-list-item-title>
                {{ item.name }}
              </v-list-item-title>
            </v-list-item-content>
          </v-list-item>
        </nuxt-link>
      </v-list>
    </v-navigation-drawer>
  </div>
</template>

<script>
export default {
  data() {
    return {
      drawer: null,
      navigates: [
        {
          name: 'Home',
          link: '/',
        },
        {
          name: 'Us',
          link: '#info',
        },
        {
          name: 'Portfolio',
          link: '#port',
        },
        {
          name: 'Contact Us',
          link: '#contact',
        },
      ],
    }
  },
}
</script>

<style>
.text-white {
  color: white !important;
}
.navigation-show {
  display: none;
}
.navigation-opacity{
    opacity: .6;
}
@media (max-width: 700px) {
  .navigation-app {
    display: none;
  }
  .navigation-show {
    display: block;
  }
}
</style>
