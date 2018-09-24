<template>
  <div id="app">
    <appHeader />
    <nuxt/>
    <appFooter />
  </div>
</template>

<script>
import appHeader from '~/components/header.vue'
import appFooter from '~/components/footer.vue'

export default {
  components: {
    appHeader,
    appFooter
  },
}
</script>
