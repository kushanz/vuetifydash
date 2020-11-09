<template>
    <div>
    <v-app-bar app color="primary" dark >
    <v-app-bar-nav-icon @click.stop="drawer = !drawer"></v-app-bar-nav-icon>
      <div class="d-flex align-center">
        <v-img
          alt="Vuetify Logo"
          class="shrink mr-2"
          contain
          src="https://cdn.vuetifyjs.com/images/logos/vuetify-logo-dark.png"
          transition="scale-transition"
          width="40"
        />
        <v-img
          alt="Vuetify Name"
          class="shrink mt-1 hidden-sm-and-down"
          contain
          min-width="100"
          src="https://cdn.vuetifyjs.com/images/logos/vuetify-name-dark.png"
          width="100"
        />
      </div>

      <v-spacer></v-spacer>

      <v-btn
        href="https://github.com/vuetifyjs/vuetify/releases/latest"
        target="_blank"
        text
      >
        <span class="mr-2">Latest Release</span>
        <v-icon>mdi-open-in-new</v-icon>
      </v-btn>
    </v-app-bar>
   <v-navigation-drawer v-model="drawer" app >
      <v-spacer style="height:60px;"></v-spacer>
      <v-list nav dense rounded >
        <v-list-item-group v-model="group" active-class="deep-purple--text text--accent-4" >
           <v-list-item 
           v-for="(item, i) in items" 
           :key="i" 
           :item="item"  link 
           @click="$router.push({ path: item.route })">
                    <v-list-item-icon>
                        <v-icon>{{ item.icon }}</v-icon>
                    </v-list-item-icon>
                    <v-list-item-content>
                        <v-list-item-title>{{ item.title }}</v-list-item-title>
                    </v-list-item-content>

                </v-list-item>
        </v-list-item-group>
      </v-list>
    </v-navigation-drawer>

    </div>
</template>

<script>

export default {
  name: 'layout',

  data: () => ({
    drawer: false,
    group: null,
    items: [
                {icon: 'mdi-home', title:'Home', route:'/'},
                {icon: 'mdi-account', title:'About', route:'/about'}
            ],
  }),
  watch: {
      group () {
        this.drawer = false
      },
    },
};
</script>
<style lang="css"> 
/* a {
  text-decoration: unset !important;
  color: unset !important;
} */


</style>
