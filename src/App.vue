<template>
  <v-app>
    <TheHeader/>
    <v-content style="background: #212121;min-height: 90vh;">
      <router-view/>
    </v-content>
    <!-- <TheFooter/> -->
  </v-app>
</template>

<script>
import TheHeader from '@/components/TheHeader';
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
    // TheFooter
  }
}
</script>