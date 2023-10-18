<script>
import HeaderComponent from "./components/HeaderComponent.vue";
import NavigationComponent from "./components/NavigationComponent.vue";
import HomeComponent from "./components/HomeComponent.vue";
import AboutMeComponent from "./components/AboutMeComponent.vue";

export default {
    data() {
        return {
        loggedIn: false,
        user: {
            name: "Unda",
            surname: "Žurevska",
            code: "IT21041",
        },
        activeTab: "home",
        };
    },
    components: {
        HeaderComponent,
        NavigationComponent,
        HomeComponent,
        AboutMeComponent,
    },
    methods: {
        login() {
        if (confirm("Do you want to log in?")) {
            this.loggedIn = true;
            this.$emit("login", this.loggedIn);
        }
        },
        logout() {
        if (confirm("Do you want to log out?")) {
            this.loggedIn = false;
            this.$emit("logout", this.loggedIn);
        }
        },
        navigate(tab) {
            this.activeTab = tab;
        },
    },
};
</script>

<template>
    <div class="app">
      <HeaderComponent :user="user" :loggedIn="loggedIn" @login="login" @logout="logout" />
        <div class="row">
          <div class="col-4">
            <NavigationComponent v-if="loggedIn" @navigate="navigate" :activeTab="activeTab" />
          </div>
          <div class="col-8">
            <div class="main-content">
              <HomeComponent v-if="loggedIn && activeTab === 'home'" />
              <AboutMeComponent v-if="loggedIn && activeTab === 'about'" :user="user" />
            </div>
          </div>
        </div>
      </div>
  </template>
  
