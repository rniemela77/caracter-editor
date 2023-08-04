<template>
  <div class="page">
    <div class="lane">
      <div class="box"></div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {};
  },
};
</script>

<style scoped>
.box {
  height: 100px;
  width: 100px;
  background: black;
}
* {
  font-size: 9vw;
}
button {
  font-size: 120%;
}
.page {
  height: 100vh;
  width: 100vw;
  overflow: hidden;
  top: 0;
  left: 0;
  position: fixed;
  display: flex;
  align-items: center;
  justify-content: center;
}
.lane {
  width: 50%;
  background: grey;
  height: 50%;
}
</style>
