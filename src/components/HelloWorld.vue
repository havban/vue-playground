<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <p>mapped: {{mappedX}}</p>
    <p>filtered: {{filteredX}}</p>
    <p>sum: {{sumX}}</p>
    <p>sumOfX: {{sumOfX}}</p>
    <p>doSumOfX: {{doSumOfX()}}</p>
    <input type="text" v-model="txt"/>
    {{txt}}
    <button @click="clickDong">Klik dong</button>
    <p>
      For a guide and recipes on how to configure / customize this project,<br>
      check out the
      <a href="https://cli.vuejs.org" target="_blank" rel="noopener">vue-cli documentation</a>.
    </p>
    <h3>Installed CLI Plugins</h3>
    <ul>
      <li><a href="https://github.com/vuejs/vue-cli/tree/dev/packages/%40vue/cli-plugin-babel" target="_blank" rel="noopener">babel</a></li>
      <li><a href="https://github.com/vuejs/vue-cli/tree/dev/packages/%40vue/cli-plugin-eslint" target="_blank" rel="noopener">eslint</a></li>
    </ul>
    <h3>Essential Links</h3>
    <ul>
      <li><a href="https://vuejs.org" target="_blank" rel="noopener">Core Docs</a></li>
      <li><a href="https://forum.vuejs.org" target="_blank" rel="noopener">Forum</a></li>
      <li><a href="https://chat.vuejs.org" target="_blank" rel="noopener">Community Chat</a></li>
      <li><a href="https://twitter.com/vuejs" target="_blank" rel="noopener">Twitter</a></li>
      <li><a href="https://news.vuejs.org" target="_blank" rel="noopener">News</a></li>
    </ul>
    <h3>Ecosystem</h3>
    <ul>
      <li><a href="https://router.vuejs.org" target="_blank" rel="noopener">vue-router</a></li>
      <li><a href="https://vuex.vuejs.org" target="_blank" rel="noopener">vuex</a></li>
      <li><a href="https://github.com/vuejs/vue-devtools#vue-devtools" target="_blank" rel="noopener">vue-devtools</a></li>
      <li><a href="https://vue-loader.vuejs.org" target="_blank" rel="noopener">vue-loader</a></li>
      <li><a href="https://github.com/vuejs/awesome-vue" target="_blank" rel="noopener">awesome-vue</a></li>
    </ul>
  </div>
</template>

<script>
import isOdd from 'is-odd-num'

const VAR_A = 4

export default {
  name: 'HelloWorld',
  data () {
    return {
      x: [1, 7, 6],
      txt: '',
      sumOfX: 0
    }
  },
  props: {
    msg: String
  },
  computed: {
    isOdd () {
      return isOdd(VAR_A)
    },
    mappedX () {
      // let newX = []
      // for (let i=0; i < this.x.length; i++) {
      //   newX.push('hello ' + this.x[i])
      // }
      // return newX

      // return this.x.map(i => 'hello ' + i)
      return this.x.map( ( i, idx) => {
        // return '[' + idx + '] hello ' + i
        return `[${idx}] hello ${i}`
      })
      // return this.x.map(function (i) {
      //   return 'hello ' + i
      // })
    },
    filteredX () {
      return this.x.filter(i => {
        return i % 2 === 0
      })
    },
    sumX () {
      return this.x.reduce((acc, i) => {
        return acc + i
      }, 0)
    }
  },
  methods: {
    clickDong () {
      this.x.push(this.txt)
    },
    doSumOfX () {
      this.sumOfX = this.x.reduce((acc, i) => {
        return acc + i
      }, 0)
      return this.sumOfX
    }
  },
  watch: {
    x () {
      this.doSumOfX()
    }
  },
  mounted () {
    this.doSumOfX()
  }
}
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
</style>
