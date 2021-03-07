<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <div v-html="`<span>1</span>`"></div>
    <div v-text="`<span>1</span>`"></div>
    <div>{{firstName}}</div>
    <div>{{lastName}}</div>
    <div>{{fullName}}</div>
    <div :class="{blue:isBlue,red:isRed}">王孟娟</div>
    <div :style="{color:isBlue? 'blue': 'red'}">王孟娟2</div>

  </div>
</template>

<script>

export default {
  name: 'App',
  components: {
  },
  data() {
    return {
       firstName: 'first',
       lastName: 'last',
       isBlue:true,
       isRed: false
    }
  },
  computed: {
    fullName() {
      return this.firstName + ' ' + this.lastName
    }
  },
  mounted(){
    setInterval(() => {
      this.isBlue = !this.isBlue;
      this.isRed = !this.isRed;
    }, 3000)
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
.blue {
  color: blue;
}
.red {
  color:red;
}
</style>
