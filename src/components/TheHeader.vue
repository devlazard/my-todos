<template>
  <v-toolbar dark flat app style="border-bottom: 1px solid darkgray">
    <v-toolbar-side-icon href="/" color="primary" style="text-align: right">
      <img src="img/logo/logo.svg" alt="My Todos" width="32px">
    </v-toolbar-side-icon>
    <v-toolbar-title style="color: lightgray">
      <span class="font-weight-light">MY</span>
      <span class="font-weight-">TODOS</span>
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
