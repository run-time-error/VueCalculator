<template>
  <div class="__calc">
    <Display :text="displayStr" :answer="ans"/>
    <NumberPallete @display="handleDisplayEvent"/>
    <button type="button" @click="handleAC">AC</button>
  </div>
</template>

<script>
import NumberPallete from "./NumberPallete";
import Display from "./Display";

export default {
  name: "Calculator",
  components: {
    NumberPallete,
    Display
  },
  data() {
    return {
      displayStr: "",
      ans: 0,
      operator: "",
      firstNum: "0",
      lastNum: ""
    };
  },
  methods: {
    handleAC() {
      this.ans = 0;
      this.displayStr = "";
      this.operator = "";
      this.firstNum = "0";
      this.lastNum = "";
    },
    isOperator(operator) {
      return (
        operator === "+" ||
        operator === "-" ||
        operator === "*" ||
        operator === "/" ||
        operator === "="
      );
    },
    handleDisplayEvent(val) {
      this.displayStr += val;
      if (this.isOperator(val)) {
        this.displayStr += " ";
        this.operator = val;

        if (this.firstNum === "") {
          this.firstNum = this.lastNum;
        } else {
          console.log(this.ans);
          console.log(this.firstNum);

          this.ans = this.execute(
            parseFloat(this.firstNum),
            parseFloat(this.lastNum),
            this.operator
          );

          this.firstNum = this.ans.toString(10);
        }

        this.lastNum = "";
      } else {
        this.lastNum += val;
      }
    },
    execute(first, second, ops) {
      console.log("first: " + first);
      console.log("last: " + second);
      console.log("ops: " + ops);

      switch (ops) {
        case "+":
          return first + second;
        case "-":
          return first - second;
        case "*":
          return first * second;
        case "/":
          return first / second;
        default:
          console.log("Def");
          return "";
      }
    }
  }
};
</script>

<style>
.__calc {
  display: flex;
  flex-direction: column;
  justify-content: center;
  width: 76vw;
  height: 50vh;
  border: 0.1vh solid #162636;
  box-sizing: border-box;
}
</style>
