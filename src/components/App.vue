<template>
  <section>
    <div class="main-container">
      <h4>Input</h4>
      <form action="" class="main-form">
        <!-- V-Model -->
        <input type="text" v-model="value" /> <br />
        <button type="button" v-on:click="addValue">submit</button>
        <!-- V-BIND -->
        <ul v-bind="key">
          <!-- v-FOR -->
          <li v-for="goal in goals" :key="goal.index">
            {{ goal }}
          </li>
        </ul>
      </form>
      <br /><br /><br />
      <h4>links</h4>
      <p>ex of dynamic</p>
      <a v-bind:href="link" target="_blank"> link</a>

      <br /><br /><br />
      <p>{{ number() }}</p>

      <!-- V-HTML -->
      <p v-html="elem"></p>
    </div>
    <!-- V-ON -->
    <div class="counter">
      <button v-on:click="counter++">add</button>
      <p>{{ counter }}</p>
      <button v-on:click="counter--">remuve</button>
    </div>
    <br /><br /><br />
    <div class="counter">
      <button v-on:click="add">add</button>
      <p>{{ counter2 }}</p>
      <button v-on:click="reduce">remuve</button>
    </div>
    <br /><br /><br />
    <div class="counter">
      <button v-on:click="add2(10)">add 10</button>
      <p>{{ counter3 }}</p>
      <button v-on:click="reduce2(10)">remuve 10</button>
      <br /><br /><br /><br />

      <input type="text" v-on:input="setName" />
      <p>your name is: {{ name }}</p>
      <br /><br /><br /><br />
      on submit
      <form v-on:submit="submitForm">
        <input type="text" />
        <button type="">sign up</button>
      </form>
      <br /><br /><br /><br />
    </div>
  </section>
</template>

<script>
export default {
  name: "app",

  data() {
    return {
      goals: [],
      value: "",
      key: 1,
      link: "https://www.google.ro",
      elem: "<h1>hello world</h1>",
      counter: 0,
      counter2: 0,
      counter3: 0,
      name: ""
    };
  },
  methods: {
    addValue() {
      this.goals.push(this.value);
      this.value = "";
    },
    add() {
      this.counter2 += 1;
    },
    reduce() {
      this.counter2 -= 1;
    },
    add2(num) {
      this.counter3 += num;
    },
    reduce2(num) {
      this.counter3 -= num;
    },
    setName(event) {
      this.name = event.target.value;
    },
    submitForm(e) {
      e.preventDefault();
      alert("Form submitted");
    },
    number() {
      const random = Math.random();
      if (random < 0.5) {
        return "learn vue";
      } else {
        return "master vue";
      }
    }
  }
};
</script>

<!-- CSS libraries -->
<style src="normalize.css/normalize.css"></style>

<!-- Global CSS -->
<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  text-transform: capitalize;
}
.main-container {
  margin-left: 50px;
  text-align: center;
  width: 30%;

  margin-top: 10vh;
}
ul {
  border: 2px solid grey;
  list-style: none;
  padding: 20px;
}
.counter {
  width: 30%;
  margin-left: 50px;
  text-align: center;
}
</style>
