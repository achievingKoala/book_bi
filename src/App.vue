<template>
  <div id="app">
    <div>
      <div class="input-row">
        巅峰表现 = 
        <el-input v-for="(input, index) in inputs" :key="index" v-model="inputs[index]" maxlength="10" placeholder="请输入内容" style="width: 200px;"> +
        </el-input>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      inputs: ['', '', '', ''],
      isRight: false
    }
  },
  watch: {
    inputs: {
      handler(newInputs) {
        const rightValues = ['1', '3', '8', '9'];
        const inputValue = newInputs.join('+');
        
        if (rightValues.join('+') === inputValue) {
          this.isRight = true;
          alert(this.isRight);
        }
      },
      deep: true
    }
  }
}
</script>

<style>
.input-row {
  display: flex;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

nav {
  padding: 30px;
}

nav a {
  font-weight: bold;
  color: #2c3e50;
}

nav a.router-link-exact-active {
  color: #42b983;
}
</style>
