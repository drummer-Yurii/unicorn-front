<template>
  <div class="container">
    <div>
      <label>
        <input type="file" id="file" ref="file" />
      </label>
    </div>
    <BaseButton @click="uploadFile()">Import</BaseButton>
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
}
</style>
