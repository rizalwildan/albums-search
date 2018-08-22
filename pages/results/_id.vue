<template>
  <div>
    <div v-if="albumExists">
      <h1 class="text-md-center text-xs-center">Results For Album {{$route.params.id}} </h1>
      <div  v-for="(isi, index) in albumData" :key="isi.collectionCensoredName">
        <album
          :title="isi.collectionCensoredName"
          :image="isi.artworkUrl100"
          :artistName="isi.artistName"
          :url="isi.artistViewUrl"
          :color="picker(index)"
        />
      </div>
    </div>
    <div v-else>
      <h1>Could Not Find Album {{$route.params.id}}</h1>
    </div>
  </div>
</template>

<script>
  import Album from '~/components/Album';
    export default {
      middleware: 'search',
      components: {
        Album
      },
      methods: {
        picker(index) {
          return index % 2 === 0 ? "blue" : "purple";
        }
      },
      computed: {
        albumExists() {
          return this.$store.state.albums.length > 0;
        },
        albumData: function() {
          return this.$store.state.albums;
        }
      }
    }
</script>

<style scoped>

</style>
