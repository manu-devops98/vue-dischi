<template>
  <select
    @change="$emit('changeSelect', selectValue)"
    v-model="selectValue"
    name="genere"
    id="genere"
  >
    <option>All</option>
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
      selectValue: "All",
    };
  },
  methods: {},
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
    width: 180px;
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
