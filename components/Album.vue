<template>
  <div
    id="e3"
    style="max-width: 400px; margin: auto;"
    class="grey lighten-3"
  >
    <v-container fluid style="min-height: 0;" grid-list-lg>
      <v-layout row wrap>
        <v-flex xs12>
          <v-card :color="color" :href="url" target="_blank" class="white--text">
            <v-layout row>
              <v-flex xs7>
                <v-card-title primary-title>
                  <div>
                    <div class="headline">{{title}}</div>
                    <div>{{artistName}}</div>
                    <div>(2013)</div>
                  </div>
                </v-card-title>
              </v-flex>
              <v-flex xs5 lg5 md5>
                <v-card-media
                  :src="image"
                  height="100px"
                  contain
                ></v-card-media>
              </v-flex>
            </v-layout>
          </v-card>
        </v-flex>
      </v-layout>
    </v-container>
  </div>

</template>

<script>
    export default {
        name: "Album",
      props: ['title', 'image', 'artistName', 'url', 'color'],
    }
</script>

<style scoped>

</style>
