<template>
  <v-container id="info">
    <h2 class="text-center text-decoration-underline" elevation="1">US</h2>
    <v-row>
      <v-col cols="12" sm="12" md="6" lg="4" v-for="(item,index) in informations" :key="index">
        <v-card class="mx-auto" max-width="344">
          <v-img
            :src="item.src"
            height="200px"
          ></v-img>

          <v-card-title>{{item.title}}</v-card-title>

          <v-card-subtitle>{{item.subtitle}}</v-card-subtitle>

          <v-card-actions>
            <v-expansion-panels>
              <v-expansion-panel>
                <v-expansion-panel-header> Details </v-expansion-panel-header>
                <v-expansion-panel-content>{{item.description}} 
                </v-expansion-panel-content>
              </v-expansion-panel>
            </v-expansion-panels>
          </v-card-actions>

        </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  data() {
    return {
      informations:[
          {
              title: 'Information 1',
              subtitle: 'Subinformation 1',
              src:'https://frutasexoticas10.com/wp-content/uploads/2017/12/Mango-Keitt.jpg',
              description:'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.'
          },
          {
              title: 'Information 2',
              subtitle: 'Subinformation 2',
              src:'https://elpoderdelconsumidor.org/wp-content/uploads/2016/02/Mangos.jpg',
              description:'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.'
          },
          {
              title: 'Information 3',
              subtitle: 'Subinformation 3',
              src:'https://gourmetdemexico.com.mx/wp-content/uploads/2017/06/mango_haden.jpg',
              description:'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.'
          }
      ]
    }
  },
}
</script>
