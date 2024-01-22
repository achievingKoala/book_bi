<template>
    <div>
        <!-- Your component's template -->
        <h1>{{ message }}</h1>
        <el-row>
            <input v-for="word in wordList" :key="word" @input="checkInput(word)">
        </el-row>
    </div>
</template>
  
<script>
export default {
    create() {
        var item2 = ["There", "are", "two", "ways", "of", "disliking", "art", "One", "is"]
        this.wordList = item2
    },
    data() {
        return {
            message: 'Hello, Vue!',
            wordList:["There", "are", "two", "ways", "of", "disliking", "art", "One", "is"]
        };
    }
};
</script>
  
  