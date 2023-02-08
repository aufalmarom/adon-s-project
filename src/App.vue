<template>
  <v-app>
    <v-main>
      <SidebarComponent />
      <v-container>
        <router-view />
      </v-container>
    </v-main>
  </v-app>
</template>

<script>
import SidebarComponent from './components/SidebarComponent.vue';

export default {
  name: 'App',
  components: {
    SidebarComponent
  }
}
</script>