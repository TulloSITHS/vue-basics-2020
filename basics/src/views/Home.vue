<template>
  <div class="container">
    <img v-bind:src="allSlots[0].image">
    <img v-bind:src="allSlots[1].image">
    <img v-bind:src="allSlots[2].image">
    <h1>Objective is to get three of the same cats in a row. Refresh to retry.</h1>
  </div>
</template>

<script>

export default {
  name: "Home",
  components: {},
  data() {
    return {
      symbols: [
          {
            image: 'https://static-cdn.jtvnw.net/emoticons/v1/1683701/3.0',
            value: 100
          },
          {
            image: 'https://static-cdn.jtvnw.net/emoticons/v1/980171/3.0',
            value: 1000
          },
          {
            image: 'https://cdn.betterttv.net/emote/5e6092d6d6581c3724bfe544/3x',
            value: 250
          },
          {
            image: 'https://cdn.betterttv.net/emote/5e5f1649d112fc372573b879/3x',
            value: 500
          },
          {
            image: 'https://cdn.betterttv.net/emote/5e6092b3d112fc372573c7f6/3x',
            value: 0
          }
      ],
      currentSymbol: "",
      allSlots: [],
    };
  },
  methods: {
    runSlots: function(){
      for (let i = 0; i < 3; i++) {
        let number = Math.floor(Math.random() * 5);
        this.currentSymbol = this.symbols[number];
        this.allSlots.push(this.currentSymbol);
        //why does Vue use variables in a way that makes God cry
        //one moment you take you're coding and then BAM undefined
        //and then you're confused because you're looking right at it??? no syntax error or anything????
        //as I type this Vue is yelling at me with 1 error and 30 warning but it runs fine in mounted so no idea what that means
      }
    },
  },
  mounted(){
    this.runSlots();
  }
};
</script>

<style lang="scss" scoped>
h1 {
  font-size: 3rem;
}
button {
  font-size: 2rem;
}
</style>