<template>
  <div class="container">
<<<<<<< HEAD
    <input v-show="isVisible" type="text" placeholder="add token" v-model="token" />
=======
    <input
      v-show="isVisible"
      class="token"
      type="text"
      placeholder="add token"
    />
>>>>>>> 05b5b66d235c59f7af2090e5b5fd5cc8cc3cbdfc
    <BaseButton @click="sendFile" class="export">Export </BaseButton>
  </div>
</template>

<script>
import BaseButton from "./BaseButton.vue";
export default {
  components: { BaseButton },
  name: "FileExport",
  data() {
    return {
      isVisible: false,
      token: '',
      file: '',
    };
  },
  methods: {
    addFile() {
  
    },

    sendFile() {
      this.isVisible = !this.isVisible;
    }
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
