<template>
  <div v-on:click="spin()">
      <FlipTextLabel :text="word" :chance=".1" :time="50"/>
  </div>
</template>

<script>
import words from "@/words";
import FlipTextLabel from "@/components/FlipTextLabel.vue";

export default {
  props: {
    trigger: Number
  },
  components: {
      FlipTextLabel
  },
  name: 'WordSpinner',
  data: function() {
      return {
          words: words,
          word: "GO!"
      }
  },
  methods: {
      spin() {
          let rndNbr = Math.floor(Math.random()*words.words.length-1)
          console.log(rndNbr)
          this.word = words.words[rndNbr].name
      }
  },
  watch: {
    trigger: function () {
      this.spin();
    },
  },
  mounted() {
      this.spin();
  }
}
</script>

<style scoped>
    div {
        font-size: 24pt;
        display:inline-block;
        margin:30px;
        border:2px solid lightblue;
        border-radius: 15px;
        padding: 10px;
        text-transform: uppercase;
    }

</style>