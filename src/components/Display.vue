<template>
  <div class="__calc-display-container">
    <span class="__calc-display-expr">{{text}}</span>
    <span class="__calc-display-ans">{{answer}}</span>
  </div>
</template>

<script>
export default {
  name: "Display",
  components: {},
  props: {
    text: String,
    answer: Number
  },
  methods: {}
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
  margin: 0.5vh 3vh;

  box-sizing: border-box;
  border: 1px solid #381781;
}

.__calc-display-expr {
  padding: 2vw;
  color: blue;
  font-size: 1.5em;
}

.__calc-display-ans {
  padding: 2vw;
  color: blue;
  font-size: 1.5em;
}
</style>
