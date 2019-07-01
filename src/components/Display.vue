<template>
  <div class="__calc-display-container">
    <span class="__calc-display">{{text}}</span>
  </div>
</template>

<script>
export default {
  name: "Display",
  components: {},
  props: {
    text: String
  },
  methods: {},
  computed: {
    textStr() {
      return this.text;
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.__calc-display-container {
  /* background-color: #efefef; */
  width: 70vw;
  height: 10vh;
  display: flex;
  flex-wrap: wrap;
  flex-direction: row-reverse;
  justify-content: flex-start;
  align-items: center;
  align-self: flex-start;
  margin: 3vh;
  box-sizing: border-box;
  border: 1px solid #381781;
}

.__calc-display {
  padding: 2vw;
  color: blue;
  font-size: 1.5em;
}
</style>
