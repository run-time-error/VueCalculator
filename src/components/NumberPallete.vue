<template>
  <div class="__calc-number-pallete">
    <CalculatorBtn
      v-for="i in reverseNumberList"
      :key="i.text"
      :btn_text="i.text"
      :btn_color="i.backColor"
      @btn-clicked="handleBtnClicked"
    />
  </div>
</template>

<script>
import CalculatorBtn from "./CalculatorButton";
export default {
  name: "NumberPallete",
  components: {
    CalculatorBtn
  },
  props: {},
  methods: {
    handleBtnClicked(val) {
      this.$emit("display", val);
    }
  },
  computed: {
    reverseNumberList() {
      let arr = [
        {
          text: "0",
          backColor: "black"
        },
        {
          text: ".",
          backColor: "black"
        },
        {
          text: "=",
          backColor: "blue"
        },
        {
          text: "1",
          backColor: "black"
        },
        {
          text: "2",
          backColor: "black"
        },
        {
          text: "3",
          backColor: "black"
        },
        {
          text: "4",
          backColor: "black"
        },
        {
          text: "5",
          backColor: "black"
        },
        {
          text: "6",
          backColor: "black"
        },
        {
          text: "7",
          backColor: "black"
        },
        {
          text: "8",
          backColor: "black"
        },
        {
          text: "9",
          backColor: "black"
        }
      ];
      return arr.slice().reverse();
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.__calc-number-pallete {
  background-color: black;
  width: 35vw;
  height: 25vh;
  display: flex;
  flex-wrap: wrap;
  flex-direction: row-reverse;
  padding: 1vh;
  margin: 0.5vh 3vh;

  justify-content: space-around;
  align-self: flex-end;
  align-items: center;

  /* align-items: center;
  justify-content: center; */
  color: white;
}
</style>
