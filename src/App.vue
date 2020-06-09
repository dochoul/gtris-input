<template>
  <div id="app">
    <h1>Input component</h1>
    <div>
      <hw-input placeholder="😍 Basic usage"/>
    </div>
    <div>
      <hw-input placeholder="😍 Small size" size="sm"/>
    </div>
    <div>
      <hw-input placeholder="😍 Large size" size="lg"/>
    </div>

    <div>
      <hw-input
        :defaultValue="defaultValue"
        v-model="defaultValue"
        placeholder="💻 keyup, press Enter key binding"
        @keyup="keyup"
        @pressEnter="pressEnter"
      />
    </div>
    <div>
      <hw-input placeholder="🍭 Custom Class" custom-class="input-custom-class"/>
    </div>
    <div>
      <hw-input placeholder="⛔ disabled" disabled/>
    </div>
  </div>
</template>

<script>
import HwInput from "./components/HwInput";

export default {
  name: "App",
  components: {
    HwInput
  },
  data() {
    return {
      defaultValue: "😍 입력창에 기본으로 들어갈 텍스트를 지정할 수 있습니다."
    };
  },
  methods: {
    pressEnter() {
      console.log("Press Enter");
      this.defaultValue = "";
    },
    keyup() {
      console.log("Key Up");
    }
  }
};
</script>

<style lang="scss" scoped>
#app {
  width: 90%;
  margin: 3em auto 0;
  align-items: center;
}
div {
  margin: 1em 0;
}
.hw-input.input-custom-class {
  border-width: 4px;
  border-color: crimson;
  &:hover {
    border-color: indigo;
  }
  &:focus {
    border-color: khaki;
  }
}
</style>
