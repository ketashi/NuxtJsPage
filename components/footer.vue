<template>
    <v-footer dark padless width="100%">
        <v-col cols="12">
      <v-card>
        <v-card-title dark>
          <strong class="subheading"
            >Get connected with us on social networks!</strong
          >

          <v-spacer></v-spacer>

          <v-btn v-for="icon in icons" :key="icon" class="mx-4" dark icon>
            <v-icon size="24px">
              {{ icon }}
            </v-icon>
          </v-btn>
        </v-card-title>

        <v-card-text class="py-2 white--text text-center">
          {{ new Date().getFullYear() }} —
          <strong>all rights reserved</strong>
        </v-card-text>
      </v-card>
      </v-col>
  </v-footer>
  
</template>

<script>
export default {
  data() {
    return {
      icons: ['mdi-facebook', 'mdi-twitter', 'mdi-linkedin', 'mdi-instagram'],
    }
  },
}
</script>
