<template>
  <div class="container">
    <input v-show="isVisible" type="text" placeholder="add token" />
    <BaseButton @click="sendFile">Export</BaseButton>
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
    };
  },
  methods: {
    sendFile() {
      this.isVisible = !this.isVisible;
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
}
</style>
