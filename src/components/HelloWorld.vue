<template>
  <div class="page">
    <div class="sigil">
      <span
        class="letter"
        v-for="(letter, index) in name"
        :class="getClassForLetter(index)"
        >{{ letter }}</span
      >
    </div>

    <div class="options">
      <div class="select-letter-options">
        <button
          :disabled="index === selectedIndex"
          v-for="(letter, index) in name"
          @click="selectLetter(index)"
        >
          {{ letter }}
        </button>
      </div>
      <div class="name">
        <input type="text" v-model="name" />
      </div>

      <div class="frame-options">
        <input type="range" min="0" max="10" />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      name: 'test',
      selection: name[0],
      selectedIndex: null,
    };
  },
  methods: {
    getClassForLetter(letterIndex) {
      if (letterIndex === this.selectedIndex) return 'highlighted';
      return '';
    },
    selectLetter(letterIndex) {
      this.selectedIndex = letterIndex;
      this.selection = name[letterIndex];
    },
  },
};
</script>

<style>
.page * {
  font-size: 100%;
}
.highlighted {
  color: red;
}
.page {
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;
}
.sigil {
  width: 66vw;
  height: 50vh;
  border: 1px solid grey;
  display: flex;
  align-items: center;
  justify-content: center;
}
.letter {
  position: absolute;
  font-size: 65vw;
}
</style>
