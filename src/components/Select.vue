<template>
  <select @click="sendSelect()" ref="selectGenere" name="genere" id="genere">
    <option value="rock">Rock</option>
    <option value="pop">Pop</option>
    <option value="metal">Metal</option>
    <option value="jazz">Jazz</option>
  </select>
</template>

<script>
export default {
  name: "Select",
  data() {
    return {
      selectValue: "Rock",
    };
  },
  methods: {
    sendSelect() {
      this.selectValue = this.$refs.selectGenere.value;
      console.log(this.selectValue);
      this.$emit("emitSelect", this.selectValue);
    },
  },
};
</script>

<style lang="scss">
.select-container {
  select {
    position: relative;
    top: 0;
    left: 40%;
    transform: translateX(-40%);
    padding: 0.4em;
    margin-top: 1em;
    width: 100px;
    background-color: #2d3a46;
    color: white;
  }
  label {
    color: white;
    position: relative;
    top: 0;
    left: 35%;
    transform: translateX(-45%);
  }
}
</style>
