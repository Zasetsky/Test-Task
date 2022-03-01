<template>
  <v-app>
    <v-main>
      <Nuxt />
    </v-main>
    <v-footer
      fixed
      class="footPagination"
    >
      <Pagination />
    </v-footer>
  </v-app>
</template>

<script>

export default {
  name: 'DefaultLayout'
}
</script>

<style lang="scss" scoped>
.footPagination {
  justify-content: center;
}
</style>
