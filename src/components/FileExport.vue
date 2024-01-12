<template>
  <div class="container">
    <input v-show="isVisible" class="token" type="text" placeholder="add token" v-model="token" />
    <BaseButton @click="sendFile" class="export">Export </BaseButton>
  </div>
</template>

<script>
import BaseButton from './BaseButton.vue';
export default {
  components: { BaseButton },
  name: 'FileExport',
  data() {
    return {
      isVisible: false,
      token: '',
      file: '',
    };
  },
  methods: {
    sendFile() {
      this.axios.get('http://127.0.0.1:8000/api/download/').then((response) => {
        this.file = response.data;
      });
      this.isVisible = true;
      if (this.token === '') {
        return;
      } else if (this.token && this.file !== '') {
        this.sendToShop();
      }
      this.isVisible = false;
    },
    sendToShop() {
      this.axios
        .post(`http://127.0.0.1:8000/api/export-to-prom/`, {
          auth_token: this.token,
          file: this.file,
        })
        .then((response) => {
          if (!response.data) {
            alert('File not uploaded.');
          } else {
            alert('File uploaded successfully.');
          }
        })
        .catch((err) => {
          console.log(err);
        });
      this.token = '';
    },
  },
};
</script>

<style lang="scss" scoped>
.container {
  min-width: 340px;
  display: flex;
  flex-direction: column;
  justify-content: flex-end;
  margin-top: 10px;
  padding-left: 20px;
}
.export {
  margin-left: 95px;
}
.token {
  background: white;
  color: #271b80;
  border: 3px solid #c9d5fd;
  border-radius: 10px;
  width: 320px;
  outline: none;
  padding: 10px;
}
</style>
