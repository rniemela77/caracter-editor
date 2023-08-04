<template>
  <div class="page" @mousemove="rotateSquare">
    <div class="center-graphic">
      <div class="center-graphic_circle"></div>
      <div class="center-graphic_square" ref="square"></div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {};
  },
  methods: {
    rotateSquare(event) {
      const square = this.$refs.square;
      const squareRect = square.getBoundingClientRect();
      const centerX = squareRect.left + squareRect.width / 2;
      const centerY = squareRect.top + squareRect.height / 2;
      const mouseX = event.clientX;
      const mouseY = event.clientY;
      const angle =
        -Math.atan2(mouseY - centerY, mouseX - centerX) * (180 / Math.PI);
      square.style.transform = `rotate(${angle}deg)`;
    },
  },
};
</script>

<style scoped>
:root {
  --primary: blue;
}
.page {
  position: fixed;
  height: 100%;
  width: 100%;
  background: black;
  top: 0;
  left: 0;
  display: flex;
  align-items: center;
  justify-content: center;
}
.center-graphic {
  position: relative;
  display: block;
}
.center-graphic_circle,
.center-graphic_square {
  width: 50vw;
  height: 50vw;
  top: 0;
  left: 0;
  border: 1px solid blue;
}
.center-graphic_circle {
  position: absolute;
  border-radius: 50%;
}
</style>
