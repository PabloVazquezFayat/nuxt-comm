<template>
  <products />
</template>

<script lang="ts">
import Vue from 'vue'
import products from '~/layout/products.vue'

export default Vue.extend({
  components: { products },
})
</script>