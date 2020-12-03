<template>
  <v-carousel cycle height="400" hide-delimiter-background show-arrows-on-hover>
    <v-carousel-item v-for="(slide, i) in slides" :key="i" :src="slide.src">
      <v-row class="fill-height" align="center" justify="center">
        <div class="display-3">{{ slide.name }}</div>
      </v-row>
    </v-carousel-item>
  </v-carousel>
</template>

<script>
export default {
  data() {
    return {
      slides: [
        {
          name: 'First Slide',
          src: 'https://www.lavanguardia.com/files/article_main_microformat/uploads/2018/06/15/5e9977f1da5cc.jpeg',
        },
        {
          name: 'Second Slide',
          src: 'https://adncuba.com/sites/default/files/styles/mg_thumb_3/public/2020-07/Mangos.jpg?itok=BKWxQzcl',
        },
        {
          name: 'Thrird Slide',
          src: 'https://storage.googleapis.com/portalfruticola/2016/04/Mangos-e1570721763384.jpg',
        },
        {
          name: 'Fourth Slide',
          src: 'https://selecciones.com.mx/wp-content/uploads/2017/08/10-beneficios-del-mango.jpg',
        },
      ],
    }
  },
}
</script>
