<template>
  <div class="container">
    <div>
      <label>
        <input type="file" id="file" ref="file" />
      </label>
      <BaseButton @click="uploadFile()">Import</BaseButton>
    </div>
  </div>
</template>

<script>
import BaseButton from './BaseButton.vue';
export default {
  components: { BaseButton },
  data() {
    return {
      file: '',
    };
  },
  methods: {
    uploadFile: function () {
      
    },
  },
};
</script>

<style lang="scss" scoped>

</style>