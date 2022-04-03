<template>
  <v-app-bar max-height="64">
    <v-app-bar-nav-icon>
      <span style="font-size: 32px">G</span>
    </v-app-bar-nav-icon>
    <div
      v-if="$route.name === 'index'"
      class="search d-flex align-center justify-end ml-auto"
    >
      <v-text-field
        v-model="search"
        hide-details="auto"
        dense
        placeholder="Поиск по постам"
        prepend-icon="mdi-magnify"
        outlined
        :append-icon="search.length ? 'mdi-close' : ''"
        @click:append="clearSearch"
      />
    </div>
  </v-app-bar>
</template>

<script>
export default {
  name: 'TheNavigation',
  computed: {
    search: {
      get() {
        return this.$store.state.query
      },
      set(value) {
        this.$store.commit('SET_QUERY', value)
      },
    },
  },
  methods: {
    clearSearch() {
      this.$store.commit('SET_QUERY', '')
    },
  },
}
</script>

<style></style>
