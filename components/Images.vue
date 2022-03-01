<template>
  <v-row>
    <v-col
      v-for="n in 10"
      :key="n"
      class="d-flex child-flex"
      cols="5"
      align-self="end"
    >
      <v-img
        :src="photos"
        aspect-ratio="1"
        class="grey lighten-2"
      >
        <template #placeholder>
          <v-row
            class="fill-height ma-0"
            align="center"
            justify="center"
          >
            <v-progress-circular
              indeterminate
              color="grey lighten-5"
            />
          </v-row>
        </template>
      </v-img>
    </v-col>
  </v-row>
</template>

<script>
import axios from 'axios'
import Pagination from './Pagination.vue'

export default {
  name: 'ImagesComponent',

  props: {
    currentPage: {
      type: Number,
      required: true
    }
  },

  data () {
    return {
      photos: {},
      Pagination
    }
  },

  mounted () {
    axios.get('https://api.unsplash.com/photos/', {
      headers: { Authorization: 'Client-ID ju3_Hf_OC1Q8eux6q8_0Y43inGwbe-Yhzsy1Jp8BgPk' },
      params: { page: this.Pagination.currentPage }
    })
      .catch(function (error) {
        console.log(error)
      })
      .then((response) => {
        this.photos = response.data[0].urls.raw
      })
  }
}
</script>
