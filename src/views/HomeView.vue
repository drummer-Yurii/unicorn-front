<template>
  <div class="home">
    <div class="header">
      <div class="logo">
        <img src="../assets/logo.svg" alt="Logo" />
        <h3>Торгуй вільно</h3>
      </div>
    </div>
    <h1 class="greeting">Welcome</h1>
    <span>
      Before add and convert files <br />
      Please Login or Register
    </span>
    <br />
    <div class="btn">
      <button @click="register">REGISTER</button>
      <button @click="login">LOGIN</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "HomeView",
  methods: {
    register() {
      this.$router.push("/register");
    },
    login() {
      this.$router.push("/login");
    },
  },
};
</script>

<style lang="scss" scoped>
.home {
  position: relative;
  display: block;
  text-align: center;
  width: 100%;
  max-width: 1000px;
  min-height: 600px;
  background-size: cover;
  background-image: url("../assets/backgroundHome.jpg");
  box-shadow: 0px 6px 12px rgba(0, 0, 0, 0.2);
  border-radius: 16px;
}
.header {
  position: relative;
  display: flex;
  align-content: start;
  width: 100%;
  max-width: 1000px;
  height: 100px;
  padding: 5px 30px;
  border-bottom: 3px solid #f3d408;
}
.header img {
  width: 45px;
}
.greeting {
  margin: 50px 0;
  font-size: 40px;
}

.btn button {
  display: inline-block;
  margin: 50px 30px auto;
  width: 150px;
  padding: 10px;
  border-radius: 8px;
  border: 0;
  background-color: #c9d5fd;
  color: #271b80;
  font-size: 20px;
  font-weight: 700;
  cursor: pointer;
  margin-bottom: 10px;
}

.btn button:hover {
  background-color: #fcf3b5;
  transition: 0.5s;
}
</style>
