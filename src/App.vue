<template>
  <v-app>
    <TheHeader/>
    <v-content style="background: #212121">
      <Home/>
      <!-- <router-view/> -->
    </v-content>
    <!-- <TheFooter/> -->
  </v-app>
</template>

<script>
import TheHeader from '@/components/TheHeader';
import Home from '@/views/Home';
// import TheFooter from '@/components/TheFooter';

export default {
  name: 'App',
  data () {
    return {
      //
    }
  },
  components: {
    TheHeader,
    Home,
    // TheFooter
  }
}
</script>