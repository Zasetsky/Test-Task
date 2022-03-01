<template>
  <v-app>
    <v-main>
      <Nuxt />
    </v-main>
    <v-footer
      fixed
      class="footPagination"
    >
      <div class="text-center">
        <v-container>
          <v-row justify="center">
            <v-col cols="8">
              <v-container class="max-width">
                <v-pagination
                  v-model="page"
                  :length="15"
                />
              </v-container>
            </v-col>
          </v-row>
        </v-container>
      </div>
    </v-footer>
  </v-app>
</template>

<script>
import axios from 'axios'

export default {
  name: 'DefaultLayout',
  data () {
    return {
      page: 1
    }
  },
  methods: {
    next (page) {
      axios.get('https://api.unsplash.com/photos/', {
        headers: { Authorization: 'Client-ID ju3_Hf_OC1Q8eux6q8_0Y43inGwbe-Yhzsy1Jp8BgPk' },
        params: { }
      })
        .then((response) => {
          this.bills = response.data.content
          console.log(this.bills)
        })
        .catch((error) => {
          console.log(error)
        })
    }
  }
}
</script>

<style lang="scss" scoped>
.footPagination {
  justify-content: center;
}
</style>
