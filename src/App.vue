<template>
  <div id="app">
    <Display :text="displayStr"/>
    <NumberPallete @display="handleDisplayEvent"/>
  </div>
</template>

<script>
import NumberPallete from "./components/NumberPallete";
import Display from "./components/Display";

export default {
  name: "App",
  components: {
    NumberPallete,
    Display
  },
  data() {
    return {
      displayStr: ""
    };
  },
  methods: {
    handleDisplayEvent(val) {
      this.displayStr += val;
      console.log(this.displayStr);
    }
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  display: flex;
  flex-direction: column;
  width: 76vw;
  height: 50vh;
  border: 1px solid #162636;
}
</style>
