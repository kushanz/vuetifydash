<template>
  <v-app>
    <layout />
    <v-main>
        <router-view/>
    </v-main>
  </v-app>
</template>

<script>
import layout from './layout/Layout';


export default {
  name: 'App',

  components: {
    layout,
  },

  data: () => ({
    //
  }),
};
</script>
