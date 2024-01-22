<template>
  <div id="app">
    <div>
      <test-view1></test-view1>
      <el-row>
        巅峰表现 =
        <el-input v-for="(input, index) in inputs" :key="index" v-model="inputs[index]" maxlength="10" placeholder="请输入内容"
          style="width: 200px;"> +
        </el-input>
        <el-button v-if="isRight" type="success" icon="el-icon-check" circle></el-button>
      </el-row>
      <el-row>
        动机 =
        <el-input v-for="(input, index) in inputs2" :key="index" v-model="inputs2[index]" maxlength="10" placeholder="请输入内容"
          style="width: 200px;"> +
        </el-input>
        <i  class="el-icon-circle-check"></i>
        <!-- v-if="isRight2" -->
      </el-row>
      <el-row>
         <span style="color: green;">内在驱动 = </span>
        <el-input v-for="(input, index) in inputs3" :key="index" v-model="inputs3[index]"  
          style="width: 200px;color: green;"> +
        </el-input>
        <i  class="el-icon-circle-check"></i>
      </el-row>
    </div>

    <input v-model="textColor" type="text" style="color: green;  font-size: 40px;">


    
  </div>
</template>

<script>
import TestView1 from './views/TestView1.vue';
export default {
  components: {
    TestView1
  },
  created() {
    var item = {
      "Chinese":"讨厌艺术的方式有两种……一种是单纯地讨厌它，另一种是理性地喜欢它",
      "English":"There are two ways of disliking art … One is to dislike it.The other is to like it rationally"
    }
    
    console.log(item);
  },
  data() {
    return {
      textColor:'sdfa',
      inputs: ['', '', '', ''],
      inputs2: ['', '', ''],
      inputs3: ['', '', '','', '', ''],
      isRight: false,
      isRight2: false,
      isRight3: false
    }
  },
  watch: {
    inputs: {
      handler(newInputs) {
        const rightValues = ['动机', '学习', '创造力', '心流'];
        const inputValue = newInputs.join('+');

        if (rightValues.join('+') === inputValue) {
          this.isRight = true;
        }
      },
      deep: true
    },
    inputs2: {
      handler(newInputs) {
        const rightValues = ['驱动力', '目标', '坚毅力'];
        const inputValue = newInputs.join('+');

        if (rightValues.join('+') === inputValue) {
          this.isRight2 = true;
        }
      },
      deep: true
    },
    inputs3: {
      handler(newInputs) {
        const rightValues = ['好奇心', '热情', '意义', '目的', '精通', '掌握感'];
        const inputValue = newInputs.join('+');

        if (rightValues.join('+') === inputValue) {
          this.isRight3 = true;
        }
      },
      deep: true
    }
  },  
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
