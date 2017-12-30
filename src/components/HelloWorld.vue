<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <h2>Essential Links</h2>
    <ul>
      <li><a href="https://vuejs.org" target="_blank">Core Docs</a></li>
      <li><a href="https://forum.vuejs.org" target="_blank">Forum</a></li>
      <li><a href="https://chat.vuejs.org" target="_blank">Community Chat</a></li>
      <li><a href="https://twitter.com/vuejs" target="_blank">Twitter</a></li>
      <br>
      <li><a href="http://vuejs-templates.github.io/webpack/" target="_blank">Docs for This Template</a></li>
    </ul>
    <h2>Ecosystem</h2>
    <ul>
      <li><a href="http://router.vuejs.org/" target="_blank">vue-router</a></li>
      <li><a href="http://vuex.vuejs.org/" target="_blank">vuex</a></li>
      <li><a href="http://vue-loader.vuejs.org/" target="_blank">vue-loader</a></li>
      <li><a href="https://github.com/vuejs/awesome-vue" target="_blank">awesome-vue</a></li>
    </ul>
    <ul>
      <li v-for="item in list" :key="item">{{item}}</li>
    </ul>
    <ul>
      <li v-for="name in user" :key="name">
        <h6>{{name}}</h6>
      </li>
    </ul>
    <input type="text" v-model="search"/>
    <h4>{{reversedString}}</h4>
    <h4>{{num}}</h4>
    <button @click="fetchMyData()">Click me!</button>
  </div>
</template>

<script>
import axios from 'axios'
export default {
  name: 'HelloWorld',
  data () {
    return {
      msg: 'shit',
      list: ['fuck', 'shit', 'ass', 'cunt', 'dildo'],
      num: 1,
      search: 'shit',
      user: {
        name: 'Uttrs'
      }
    }
  },
  methods: {
    myClickFunction () {
      this.num++
      console.log('I am working')
    },
    fetchMyData () {
      axios.get('https://jsonplaceholder.typicode.com/')
        .then((response) => {
          console.log(response)
        })
        .catch((error) => {
          console.log(error)
        })
    }
  },
  computed: {
    reversedString () {
      return this.search.split('').reverse().join('')
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
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
</style>
