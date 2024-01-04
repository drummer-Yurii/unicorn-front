<template>
  <form @submit.prevent="Register">
    <h1>Register</h1>
    <div class="form-group">
      <label>Your name: </label>
      <input type="text" placeholder="Enter Your name" v-model="username" />
    </div>
    <div class="form-group">
      <label>Password: </label>
      <input type="password" placeholder="Password" v-model="password" />
    </div>
    <div>
      <input type="submit" value="Register" />
    </div>
    <p>Have an account? <router-link to="/login">Login Here</router-link></p>
  </form>
</template>

<script>
import axios from 'axios';
export default {
  name: 'RegisterView',
  data() {
    return {
      username: '',
      password: '',
    }
  },
  methods: {
    Register() {
      axios
        .post(`http://127.0.0.1:8000/api/signup/`, {
          headers: { 'Content-type': 'application/json' },
          'username': this.username,
          'password': this.password,
        })
        .then((response) => {
          console.log(response);
          this.$router.push('/login');
        })
        .catch((err) => {
          console.log(err);
          this.err = err;
        });
    }
  }
};
</script>

<style lang="scss" scoped>
form {
  display: block;
  width: 100%;
  max-width: 400px;
  padding: 50px 30px;
  background-image: linear-gradient(to bottom, #00bc7e, #108775);
  box-shadow: 0px 6px 12px rgba(0, 0, 0, 0.2);
  border-radius: 16px;
}

form h1 {
  color: #fff;
  font-size: 36px;
  text-transform: uppercase;
  margin-bottom: 30px;
}

form .form-group {
  margin-bottom: 30px;
}

form label {
  display: block;
  color: #eee;
  font-size: 18px;
  margin-bottom: 5px;
}

form input {
  appearance: none;
  background: none;
  outline: none;
  border: none;
}

form input:not([type='submit']) {
  display: block;
  width: 100%;
  padding: 15px;
  border-radius: 8px;
  background-color: rgba(0, 0, 0, 0.2);
  box-shadow: 0px 0px 0px rgba(0, 0, 0, 0);
  transition: 0.4s;
  color: #222;
  font-size: 14px;
  font-weight: 300;
}

form input:not([type='submit'])::placeholder {
  color: #ccc;
}

form input:not([type='submit']):focus,
form input:not([type='submit']):valid {
  color: #fff;
  box-shadow: 0px 6px 12px rgba(0, 0, 0, 0.2);
}

form input[type='submit'] {
  display: block;
  width: 100%;
  padding: 15px;
  border-radius: 8px;
  background-color: #2f4960;
  box-shadow: 0px 0px 0px rgba(0, 0, 0, 0);
  transition: 0.4s;
  color: #fff;
  font-size: 20px;
  font-weight: 700;
  cursor: pointer;
  margin-bottom: 10px;
}
</style>
