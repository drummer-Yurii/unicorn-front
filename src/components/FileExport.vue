<template>
  <div class="container">
    <div>
      <input v-show="isVisible" type="text" placeholder="add token" />
      <BaseButton @click="sendFile">Export</BaseButton>
    </div>
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
    };
  },
  methods: {
    sendFile() {
        this.isVisible = !this.isVisible;
    }
  }
};
</script>

<style lang="scss" scoped>

</style>
