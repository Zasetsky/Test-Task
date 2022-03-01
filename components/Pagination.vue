<template>
  <div class="text-center">
    <v-container>
      <v-row justify="center">
        <v-col cols="8">
          <v-container class="max-width">
            <v-pagination
              v-model="currentPage"
              :length="15"
              @input="handlePageChange"
            />
          </v-container>
        </v-col>
      </v-row>
    </v-container>
  </div>
</template>

<script>
export default {
  name: 'PaginationComponent',
  data () {
    return {
      currentPage: 1
    }
  },

  methods: {
    handlePageChange (value) {
      this.currentPage = value
    }
  }
}
</script>
