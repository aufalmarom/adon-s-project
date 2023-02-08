<template>
    <v-app-bar
        color="primary"
        prominent
      >
        <v-app-bar-nav-icon variant="text" @click.stop="drawer = !drawer"></v-app-bar-nav-icon>
        <v-toolbar-title style="cursor: pointer" >MEVN Exercise</v-toolbar-title>
        
      </v-app-bar>

      <v-navigation-drawer
        v-model="drawer"
        location="left"
        permanent
      >
        <v-list>
            <v-list-item to="/">
              <v-list-item-title>Home</v-list-item-title>
            </v-list-item>
            <v-list-item to="/login">
                <v-list-item-title>Login</v-list-item-title>
            </v-list-item>
        </v-list>
        <!-- <v-row class="text-center">
          <v-col>
            <v-btn 
              variant="flat"
              color="error"
            >
                Logout
            </v-btn>
          </v-col>
        </v-row> -->
      </v-navigation-drawer>
</template>

<script>
    export default{
        data: () => ({
            drawer: false,
            group: null
        }),
        watch: {
            group() {
                this.drawer = false
            }
        }
    }
</script>