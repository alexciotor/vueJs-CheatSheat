<template>
  <section>
    <div class="main-container">
      <h4>goal</h4>
      <form action="" class="main-form">
        <input type="text" v-model="value" /> <br />
        <button type="button" v-on:click="addValue">submit</button>

        <ul v-bind="key">
          <li v-for="goal in goals" :key="goal.index">
            {{ goal }}
          </li>
        </ul>
      </form>
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
      key: 1
    };
  },
  methods: {
    addValue() {
      this.goals.push(this.value);
      this.value = "";
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
</style>
