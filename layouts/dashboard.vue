<template>
  <v-app dark>
    <div class="d-flex">
      <v-navigation-drawer
        v-bind:width="320"
        v-model="drawer"
        :mini-variant="miniVariant"
        :clipped="clipped"
        fixed
        app
      >
        <SideBar></SideBar>
      </v-navigation-drawer>
      <v-app-bar :clipped-left="clipped" fixed app>
        <v-app-bar-nav-icon @click.stop="drawer = !drawer" />
        <v-btn icon @click.stop="miniVariant = !miniVariant">
          <v-icon>mdi-{{ `chevron-${miniVariant ? "right" : "left"}` }}</v-icon>
        </v-btn>
        <img src="/logo.png" height="45" alt="" />
        <v-spacer />
        <UserMenu />
      </v-app-bar>
      <v-main>
        <v-container>
          <Nuxt />
        </v-container>
      </v-main>
      <v-footer :absolute="!fixed" app>
        <span>&copy; {{ new Date().getFullYear() }}</span>
      </v-footer>
    </div>
  </v-app>
</template>

<script>
export default {
  name: "DashboardLayout",
  data() {
    // TODO: Implement routes here
    return {
      user: this.$auth.user,
      clipped: true,
      drawer: true,
      fixed: false,
      miniVariant: false,
    };
  },
  mounted() {
    console.log(this.$auth.user);
    if (!this.$auth.user) {
      return this.$router.push("/login");
    }
  },
  methods: {
    doLogout: function () {
      this.$auth.logout().then(() => {
        this.redirect("/login");
      });
    },
  },
};
</script>
