<template>
  <v-app>
    <v-carousel v-model="model" next prev height="500px">
      <v-carousel-item v-for="(color, i) in colors" :key="color">
        <v-sheet :color="color" height="500px" tile>
          <v-row class="fill-height" align="center" justify="center">
            <div class="text-h2">Slide {{ i + 1 }}</div>
          </v-row>
        </v-sheet>
      </v-carousel-item>
    </v-carousel>
  </v-app>
</template>

<script>
export default {
  data: () => ({
    model: 0,
    colors: ['red', 'green', 'blue', 'pink', 'orange'],
  }),
}
</script>

<style>
.v-application--wrap {
  min-height: unset;
}
</style>