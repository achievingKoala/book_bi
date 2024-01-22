<template>
    <div>
        <!-- Your component's template -->
        
        <input type="text" 
        v-model="textInput"
         :style="{ color: textInput === answer ? 'green' : 'blue', 
         fontSize: 'larger', width: '300px' }">
         <el-row>
             <!-- <h5 v-for="sentence in sentenceList">{{ sentence }}</h5> -->
             
            <input v-for="(sentence,index) in sentenceList" v-model="answerList[index]"  :key="index" :style="{ color : answerList[index] === sentenceList[index] ? 'green' : 'red'}">

             
         </el-row>
    </div>
</template>
  
<script>
export default {
    created() {
        var item2 = ["There", "are", "two", "ways", "of", "disliking", "art", "One", "is"]
        this.sentenceList = ['There are two ways of disliking art', "One is to dislike it", "The other is to like it rationally"]
        this.answerList = ['', '', '']
    },
    data() {
        return {
            textInput:'',
            answer:'There are two ways of disliking art',
            message: 'Hello, Vue!',
            sentenceList:[],
            answerList:[]
        };
    }
    
};
</script>
  
  