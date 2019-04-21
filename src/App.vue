<template>
  <v-app>
    <TheHeader/>
    <v-content style="background: #212121">
      <Home/>
    </v-content>
  </v-app>
</template>

<script>
import TheHeader from '@/components/TheHeader';
import Home from '@/views/Home';

export default {
  name: 'App',
  components: {
    TheHeader,
    Home,
  }
}
</script>