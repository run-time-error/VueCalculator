<template>
  <div class="__calc-btn" @click="onClick" :style="{'background-color': btn_color}">{{btn_text}}</div>
</template>

<script>
export default {
  name: "CalculatorButton",
  props: {
    btn_text: String,
    btn_color: String
  },
  methods: {
    onClick() {
      this.$emit("btn-clicked", this.btn_text);
    },
    
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.__calc-btn {
  background-color: black;
  width: 11vw;
  height: 5vh;
  display: flex;
  align-items: center;
  justify-content: center;
  color: white;
  border: 1px solid #cccccc;
}
</style>
