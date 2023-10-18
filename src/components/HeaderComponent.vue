<script>
    export default {
      props: ["user", "loggedIn"],
      computed: {
          full_name() {
          return `${this.user.name} ${this.user.surname}`;
          },
      },
      methods: {
          login() {
            this.$emit("login");
          },
          logout() {
            this.$emit("logout");
          },
      },
    };
</script>

<template>
  <header class="header" :style="{ backgroundColor: loggedIn ? '#7448E0' : '' }">
    <div class="header-left">
      <img class="logo" src="@/assets/logo.svg" alt="Logo" />
      <h1>KRAKEN</h1>
    </div>
    <div class="header-right">
      <div class="avatar" :style="{ backgroundColor: 'your-color' }" v-if="loggedIn">
        {{ user.name.charAt(0) }}
      </div>
      <div class="user-name" v-if="loggedIn">{{ full_name }}</div>
      <div class="vl" v-if="loggedIn"></div>
      <button @click="loggedIn ? logout() : login()" class="login-button" :style="{ backgroundColor: loggedIn ? '#191621' : '' }">
        {{ loggedIn ? "LOGOUT" : "LOGIN" }}
      </button>
    </div>
  </header>
</template>

<style>
.header {
  background-color: #45404B; 
  color: #ffffff;
  padding: 20px;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.logo {
  width: 60px;
  height: auto;
}

.header h1 {
  font-size: 24px;
  margin-left: 10px;
}

.header .avatar {
  width: 50px;
  height: 50px;
  border-radius: 50%;
  background-color: #ffffff;
  margin-right: 20px;
  display: flex;
  align-items: center;
  justify-content: center;
  text-align: center;
  font-size: 30px;
  color: #c0c0c0;
}

.header .user-name {
  font-size: 20px;
  color: #ffffff;
}

.header-left {
  display: flex;
  align-items: center;
}

.header-right {
  display: flex;
  align-items: center;
}

.header .login-button {
  background-color: #7448E0;
  color: #ffffff;
  padding: 10px 40px;
  border-radius: 25px; 
  border: none;
  cursor: pointer;
}

.header .login-button:hover {
  background-color: #6540c3;
}

.vl {
  border-left: 2px solid white;
  height: 40px;
  margin: 0 20px;
}

</style>
