<template>
  <div class="home">
    <div class="header">
      <div class="logo">
        <img src="../assets/logo.svg" alt="Logo" />
        <h3>Торгуй вільно</h3>
      </div>
      <div class="btn logout" @click="Logout">Logout</div>
    </div>
    <h1 class="greeting">Welcome</h1>
    <br />
    <div class="btn">
      <FileUpload />
      <FileExport />
    </div>
    <div class="info">
      Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut
      labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco
      laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in
      voluptate velit esse cillum dolore eu fugiat nulla pariatur.
    </div>
  </div>
</template>

<script>
import FileExport from '../components/FileExport.vue';
import FileUpload from '../components/FileUpload.vue';
export default {
  name: 'HomeView',
  components: {
    FileExport,
    FileUpload,
  },
  methods: {
    Logout() {
      localStorage.removeItem('token');
      this.$router.push('/');
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
  background-image: url('../assets/backgroundHome.jpg');
  box-shadow: 0px 6px 12px rgba(0, 0, 0, 0.2);
  border-radius: 16px;
}
.header {
  position: relative;
  display: flex;
  align-items: flex-end;
  justify-content: space-between;
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

.btn {
  display: flex;
}
.logout {
  width: 100px;
  border: 0;
  color: #271b80;
  font-weight: 700;
  cursor: pointer;
}
.logout:hover {
  color: #000;
  transition: 0.5s;
}

.info {
  width: 70%;
  margin: 0 auto;
  padding: 50px;
}
</style>
