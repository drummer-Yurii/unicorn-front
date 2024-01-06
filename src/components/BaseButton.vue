<template>
  <button><slot /></button>
</template>

<script>
export default {
  name: 'BaseButton',
};
</script>

<style lang="scss" scoped>
button {
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
  text-transform: uppercase;
}
button:hover {
  background-color: #fcf3b5;
  transition: 0.5s;
}
</style>
