<template>
  <v-toolbar dark flat app style="border-bottom: 2px solid white">
    <v-toolbar-side-icon href="/">
      <img src="img/logo/logo.svg" alt="" width="36px">
    </v-toolbar-side-icon>
    <v-toolbar-title style="color: white">
      <span>MY</span>
      <span class="font-weight-light">TODOS</span>
    </v-toolbar-title>
  </v-toolbar>
</template>
<script>
export default {
  props: {
    value: {
      type:Number,
      default: 100
    }
  }
}
</script>
