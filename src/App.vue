<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <TheButton
      label="hello"
      code="A"
      :selectedCode="selectedCode"
      @myclick="selectCode">
      <TheButton
        label="apasih"
        code="B"
        :selectedCode="selectedCode"
        @myclick="selectCode">
        <TheButton
          label="gitudong"
          code="C"
          :selectedCode="selectedCode"
          @myclick="selectCode">
          okede
        </TheButton>
      </TheButton>
      <TheButton
          label="gini sih"
          code="D"
          :selectedCode="selectedCode"
          @myclick="selectCode">
        <TheButton
            label="o gni"
            code="E"
            :selectedCode="selectedCode"
            @myclick="selectCode">
          oke yuk
        </TheButton>
      </TheButton>
    </TheButton>
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import TheButton from './components/TheButton'

export default {
  name: 'App',
  data () {
    return {
      selectedCode: ''
    }
  },
  components: {
    TheButton
  },
  methods: {
    selectCode (val) {
      console.log(val)
      this.selectedCode = val
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
