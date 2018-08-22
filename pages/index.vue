<template>
  <div>
    <v-layout align-center justify-center>
      <v-flex xs12 sm6 md3>
      <h1 class="text-md-center text-xs-center">Search iTunes</h1>
        <v-form @submit.prevent="submit">
          <v-text-field v-model="search" :rules="searchRules" label="Search" single-line required append-icon="search"></v-text-field>
        </v-form>
      </v-flex>
    </v-layout>
  </div>
</template>

<script>
export default {
  components: {
  },
  data() {
    return {
      valid: false,
      search: '',
      searchRules: [
        v => !!v || 'Cannot Empty'
      ],
    }
  },
  methods: {
    submit(event) {
      this.$router.push(`results/${this.search}`);
    }
  }
}
</script>

<style>
  h1 {
    padding: 20px;
  }
</style>

