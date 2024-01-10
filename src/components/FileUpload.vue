<template>
  <div class="container">
    <div>
      <label>
        <input type="file" id="file" ref="file" />
      </label>
    </div>
    <BaseButton @click="uploadFile()" class="import">Import</BaseButton>
  </div>
</template>

<script>
import BaseButton from "./BaseButton.vue";
export default {
  components: { BaseButton },
  data() {
    return {
      file: "",
    };
  },
  methods: {
    uploadFile: function () {},
  },
};
</script>

<style lang="scss" scoped>
.container {
  display: flex;
  flex-direction: column;
  justify-content: flex-end;
  margin-top: 10px;
  padding-right: 20px;
}
.import {
  margin-left: 95px;
}
#file {
  background: white;
  color: #271b80;
  border: 3px solid #c9d5fd;
  border-radius: 10px;
  width: 300px;
  outline: none;
}

::-webkit-file-upload-button {
  cursor: pointer;
  background: #c9d5fd;
  border-radius: 10px;
  padding: 10px;
  border: none;
}
</style>
