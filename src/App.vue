<template>
  <div id="app">
    <SaveMoney />
  </div>
</template>

<script>
import SaveMoney from "./components/saveMoney.vue";

export default {
  name: "App",
  components: {
    SaveMoney,
  },
};
</script>

<style lang="scss">
* {
  padding: 0;
  margin: 0;
}
#app {
  background: #ff3333;
}
</style>
