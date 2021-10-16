<template>
  <div class="home">
    <Navbar :fluggen="fluggen" />
    <HeroBanner />
    <Categories />
    <Featured />
    <Footer />
  </div>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  data() {
    return {
      fluggen: { name: 'Fluggen', surname: 'Kachenholen' },
    }
  },
})
</script>