<script >
export default {
  data() {
    return {
      word: {},
      isMeaningShown: false,
      words: [
        {
          english: 'to sit',
          spanish: 'sentar',
        },
        {
          english: 'hunger',
          spanish: 'hambre',
        },
        {
          english: 'style',
          spanish: 'estilo',
        }
      ]
    }
  },
  // computed: {
  //   randomWord() {
  //     const spanishWord = this.words[Math.floor(Math.random() * this.words.length)].english;
  //   }
  // }
  methods: {
    showMeaning() {
      this.isMeaningShown = true;
    }
  },
  mounted() {
    this.word = this.words[Math.floor(Math.random() * this.words.length)];
  }
}
</script>

<template>
  <div class="toggle">
    <label class="switch">
      <input type="checkbox">
      <span class="slider round"></span>
    </label>
  </div>

  <div class="word">{{ word.english }}</div>
  <div class="meaning" :class="{ show: isMeaningShown }">{{ word.spanish }}</div>
  <div class="nav">
    <button  style="display: block;" :class="{}" @click="showMeaning">Mostrar</button>
    <button  style = "visibility: hidden" @click="chooseNextWord">Siguiente</button>
  </div>
</template>

<style scoped>
  .meaning {
    visibility: hidden;
  }

  .show {
    visibility: visible;
  }

  .remove {
    display: none;
  }
</style>
