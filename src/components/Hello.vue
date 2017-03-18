<template>
  <div class="test">
    <h1>{{ title }}</h1>
    <input type="text" v-model="title"> <br>
    <h2>My name is {{ user.name }}</h2>
    <p v-if="showName">{{user.age}}</p>
    <p v-else="showName">Nobody</p>
    <ul>
      <li v-for="item in items">{{item.title}}</li>
    </ul>
    <button v-on:click="greet('Hello World')" type="button">Say Greeting</button>
    <input type="text" v-on:keyup.enter="enterHit">
    <hr>
    <label for="name">First Name</label><input type="text" name="name" v-model="user.name">
    <label for="age">Age</label><input type="text" name="age" v-model="user.age">
    <h3>{{ userProfile }}</h3>
  </div>
</template>

<script>
export default {
  name: 'hello',
  data () {
    return {
      title: 'Hello World',
      user: {
        name: 'Lina',
        age: 21
      },
      showName: true,
      items: [
        {title: 'Item1'},
        {title: 'Item2'},
        {title: 'Item3'},
        {title: 'Item4'},
        {title: 'Item5'}
      ]
    }
  },
  methods: {
    greet: (greeting) => {
      alert(greeting)
    },
    enterHit: (e) => {
      console.log(e.target.value)
    }
  },
  computed: {
    userProfile: function () {
      return `${this.user.name} is ${this.user.age}`
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}
</style>
