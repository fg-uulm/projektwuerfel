<template>
  <div v-on:keyup="trigger()">
    <h1>Dein nächstes Projekt dreht sich um...</h1>
    <word-spinner :key="`spin-${n}`" v-for="n in nbrOfSpinners" :trigger="rnd"></word-spinner>
    <hr/>
    Wieviele Begriffe? <input type="number" min="1" max="6" v-model.number="nbrOfSpinners" />
    <button v-on:click="trigger()">Neu würfeln</button>
    <div><small><strong>Tipp: auf einen einzelnen Begriff klicken um nur diesen Begriff neu zu würfeln :)</strong></small></div>
  </div>
</template>

<script>
import WordSpinner from './WordSpinner.vue'
export default {
  components: { WordSpinner },
  name: 'ProjectSpinner',
  data: function() {
    return {
      nbrOfSpinners: 3,
      rnd: 0
    }
  },
  methods: {
    trigger() {
      this.rnd = Math.random()
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  button {
    width: 10rem;
    height: 3rem;
    font-size: 20pt;
  }

  input {
    margin:20px;
    width: 3rem;
    height: 2rem;
    font-size: 20pt;
  }

  hr {
    width:50%;
    margin-top: 3rem;
    margin-bottom: 1rem;
  }

  h1 {
    font-weight: 200;
  }
</style>
