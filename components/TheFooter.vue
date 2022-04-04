<template>
  <v-footer padless>
    <v-card flat tile class="width-full text-center">
      <v-btn
        v-for="link in links"
        :key="link.href"
        :href="link.href"
        target="_blank"
        text
        rounded
        class="my-2"
      >
        {{ link.name }}
      </v-btn>

      <v-divider></v-divider>

      <v-card-text>
        {{ new Date().getFullYear() }} — <strong>GrinMorg's webdev blog</strong>
      </v-card-text>
    </v-card>
  </v-footer>
</template>

<script>
export default {
  name: 'TheNavigation',
  data() {
    return {
      links: [
        {
          name: 'Портфолио',
          href: 'https://portfolio-61b97.web.app'
        },
        {
          name: 'Блог',
          href: '/'
        },
      ]
    }
  },
}
</script>

<style></style>
