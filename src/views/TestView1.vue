<template>
    <div>
        <!-- Your component's template -->
        <!-- <textarea cols= "100" type="text" v-model="textInput" :style="{
            color: textInput === answer ? 'green' : 'blue',
            fontSize: 'larger', width: '300px',
            height: '200px' 
        }"></textarea> -->
        
        <hr>
        <span v-for="(sentence, index) in sentenceList" :key="index">
            <textarea v-model="answerList[index]" :key="index"
                :style="{ color: answerList[index] === sentenceList[index] ? 'green' : 'red', width: '1000px', height :'100px', fontSize : '40px' }">
            </textarea>
            <hr>
            {{sentenceList[index]}}    
            <hr>
        </span>
    </div>
</template>
  
<script>
export default {
    created() {

        // todo 
        /**
         * color to word
         */
        var testList1 = ["There are only two kinds of people who are really fascinating", "people who know absolutely everything and people who know absolutely nothing"]
        var testList1 = ["It is absurd to divide people into good and bad", "People are whether charming or tedious"]
        var testList1 = ["The public have an insatiable curiosity to know everything", "except what is worth knowing"]
        var testList1 = ["It is only shallow people who require years to get rid of an emotion", "A man who is master of himself can end a sorrow as easily as he can invent a pleasure"]
        
        var item2 = ["There", "are", "two", "ways", "of", "disliking", "art", "One", "is"]
        // this.sentenceList = ['There are two ways of disliking art', "One is to dislike it", "The other is to like it rationally"]
        // this.answerList = ['', '', '']        
        let myList = Array(testList1.length).fill("");
        this.answerList = myList;
        this.sentenceList = testList1;
    },
    data() {
        return {
            textInput: '',
            answer: 'There are two ways of disliking art',
            message: 'Hello, Vue!',
            sentenceList: [],
            answerList: []
        };
    }

};
</script>
  
  