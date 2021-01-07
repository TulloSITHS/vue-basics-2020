<template>
  <div class="container">
    <img :src="slots[0].image" />
    <img :src="slots[1].image" />
    <img :src="slots[2].image" />
    <button @click="runSlots">Go!</button>
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
      slots: []
    };
  },
  methods: {
    runSlots: function(){
      for (let i = 0; i < 3; i++) {
        let number = Math.floor(Math.random() * 5);
        this.currentSymbol = this.symbols[number];
        this.slots.push(this.currentSymbol);
      }
    }
  },
  created() {},
  mounted() {},
  beforeCreate() {},
};
</script>

<style lang="scss" scoped>
button {
  font-size: 2rem;
}
</style>
