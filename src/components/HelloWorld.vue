<template>
  <div class="hello">
    <p>Hello {{ name }} you have {{ age }}</p>
    <p v-text="band"></p>

    <i v-if="mode == 1"> {{ name }} :</i>
    <i v-else-if="mode == 2"> {{ age }} : </i>
    <i v-else> {{ band }} : </i>
    <select name="" id="" v-model="mode">
      <option value="1">Name</option>
      <option value="2">age</option>
      <option value="3">band</option>
    </select>

    <h1 :class="status">My status</h1>

    <button v-bind:disable="isDisable">binding value</button>
    <h1 v-bind:class="isPromoted && 'notPromoted'">Not Promoted?</h1>
    <h1 v-bind:class="isPromoted ? 'promoted' : 'notPromoted'">
      Promoted Movies
    </h1>
    <h1 v-bind:class="[isPromoted && 'promoted', notPromoted && 'notPromoted']">
      Que pasa?
    </h1>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  data() {
    return {
      name: "Paulo",
      age: 35,
      band: "The Strokes",
      mode: 1,
      isDisable: false,
      status: "danger",
      isPromoted: true,
      notPromoted: false,
    };
  },
  methods() {
    this.name;
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
.danger {
  color: red;
}
.promoted {
  font-style: italic;
  color: blue;
}

.notPromoted {
  color: red;
}
</style>
