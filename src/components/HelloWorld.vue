<template>
  <div class="hello">
    <p>Hello {{ name }} you have {{ age }}</p>
    <p v-text="band"></p>

    <i v-if="mode == 1" :class="status"> {{ name }} :</i>
    <i v-else-if="mode == 2" :class="notPromoted"> {{ age }} : </i>
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

    <h2
      v-bind:class="{
        promoted: isPromoted,
        new: !notPromoted,
        notPromoted: notPromoted,
      }"
    >
      Moto Mami
    </h2>
    <div
      :style="{
        padding: '1.5em',
        backgroundColor: '#3590f3',
        color: '#FFFFFF',
        fontSize: mySize + 'px',
      }"
    >
      This looks like a Button
    </div>

    <h1 :style="[badeStyleObject, successObject]">style Object</h1>

    <h1 v-if="num == 0">The number is zero</h1>
    <h1 v-else-if="num == 1">The number is one</h1>
    <h1 v-else-if="num == 2">The number is two</h1>
    <h1 v-else>this is not a number</h1>

    <template v-if="display">
      <h2>One</h2>
      <h2>Two</h2>
      <h2>Three</h2>
    </template>

    <div :style="[badeStyleObject, successObject]">
      <ul v-for="(person, index) in people" :key="index">
        <!-- <li v-for="(person, value) in people" :key="value">
          {{ name }}: {{ age }} {{ index }}</li>

        <hr /> -->
        <li :style="{color: 'white'}" v-if="person.age >= 21 && 'canDrink'">
          {{ person.name }} : {{ person.age }} {{ person.canDrink }}
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  data() {
    return {
      name1: "Paulo",
      age2: 35,
      band: "The Strokes",
      mode: 1,
      isDisable: false,
      status: "danger",
      isPromoted: true,
      notPromoted: false,
      mySize: 20,
      num: 1,
      display: true,
      canDrink: true,
      cantDrink: false,

      baseStyleObject: {
        color: "orange",
        fontSize: " 20ps",
        padding: " 10px",
      },
      successObject: {
        color: "green",
        backgroundColor: "lightgreen",
        border: "1px solid darkgreen",
        padding: " 20px",
      },
      people: [
        {
          name: "John",
          age: 18,
        },
        {
          name: "Maria",
          age: 21,
        },
        {
          name: "Charles",
          age: 40,
        },
        {
          name: "Astile",
          age: 89,
        },
      ],
    };
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
.bg{
  background-color: blue;
}
</style>
