<template>
  <v-container id="port">
      <div></div>
    <h2 class="text-center text-decoration-underline" elevation="1">
      Portfolio
    </h2>
    <v-row>
      <v-col cols="12">
        <v-sheet class="mx-auto" elevation="8">
          <v-slide-group v-model="model" class="pa-2" mandatory show-arrows>
            <v-slide-item
              v-for="(n, index) in portfolios"
              :key="index"
              v-slot:default="{ toggle }"
            >
              <v-card
                class="ma-4"
                height="200"
                width="100"
                @click="toggle"
                v-on:click="ClickMe"
              >
                <v-img :src="n.src" height="200"> </v-img>
              </v-card>
            </v-slide-item>
          </v-slide-group>
        </v-sheet>
        <!-- View modal image Portfolio -->
        <v-dialog v-model="dialog" width="600px">
          <v-card elevation="2">
            <v-img :src="portfolio.src" height="auto">
              <v-card-title>{{ portfolio.title }}</v-card-title>
            </v-img>
          </v-card>
        </v-dialog>
      </v-col>
    </v-row>
  </v-container>
</template>
<script>
export default {
  data() {
    return {
      model: '',
      dialog: false,
      portfolios: [
        {
          src:
            'http://www.2000agro.com.mx/wp-content/uploads/mango-soconusco.jpg',
          title: 'Magos Temporada 1',
        },
        {
          src:
            'https://world-crops.com/wp-content/uploads/32-Phitsanulok-mango-fruits.jpg',
          title: 'Magos Temporada 2',
        },
        {
          src:
            'https://blog.freshdirect.com/wp-content/uploads/2017/05/mango-smoothie-2-1080x1080.jpg',
          title: 'Magos Temporada 3',
        },
        {
          src:
            'https://www.revistamercados.com/wp-content/uploads/2018/10/LuzTropical.jpg',
          title: 'Magos Temporada 4',
        },
        {
          src:
            'https://www.adamtropics.com/images/stories/virtuemart/product/Mango%20Tree%20-%20Thailand.jpg',
          title: 'Magos Temporada 5',
        },
        {
          src:
            'https://img.chefkoch-cdn.de/rezepte/951521200670250/bilder/1207803/crop-960x720/mango-bananen-smoothie.jpg',
          title: 'Magos Temporada 6',
        },
        {
          src: 'https://i.ytimg.com/vi/jRuKjrqkJ08/maxresdefault.jpg',
          title: 'Magos Temporada 7',
        },
      ],
      portfolio: {},
    }
  },
  methods: {
    ClickMe() {
      this.dialog = true
      var data = this.portfolios.filter((item, index) => index === this.model)
      this.portfolio = data[0]
    },
  },
}
</script>
