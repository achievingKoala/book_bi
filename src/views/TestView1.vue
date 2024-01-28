<template>
    <div @keydown="keyMonitor">
        <!-- Your component's template -->
        <!-- <textarea cols= "100" type="text" v-model="textInput" :style="{
            color: textInput === answer ? 'green' : 'blue',
            fontSize: 'larger', width: '300px',
            height: '200px' 
        }"></textarea> -->
        <!-- <div v-html="htmlContent"></div> -->
        
        {{ htmlContent }}
        <!-- <medium-editor :text="htmlContent" :content="htmlContent" v-on:edit="logChange"></medium-editor> -->
        <textarea v-model="htmlContent"></textarea>    
        <div v-html="htmlContent" contenteditable="true"></div>

    
        <!-- <el-button ref="myButton">哈哈哈</el-button> -->

        <!-- <textarea> <h3>hello</h3> 009 wfw3 <span style="color: green;">9</span></textarea> -->
        {{ index }}
        <hr>
        <span v-for="(sentence, index) in sentenceList" :key="index">
            <textarea v-model="answerList[index]" :key="index"
                :style="{ color: answerList[index] === sentenceList[index] ? 'green' : 'red', width: '1000px', height :'150px', fontSize : '40px' }">
            </textarea>
            <i class="el-icon-circle-check" :style="{color: answerList[index] === sentenceList[index] ? 'green' : 'black', fontSize: '4em' }"></i>
            
            <hr>
            {{sentenceList[index]}}    
            <hr>
        </span>
        <el-button @click="goToLast">last</el-button>
        <el-button @click="goToNext">next</el-button>
        <div style="border: 1px solid #CBCBCB;height: 200px;width: 400px" contenteditable="true" >
            <span contenteditable="false" >投入：</span><span style="color: red">500</span>
        </div>
    </div>
</template>
  
<script>

import MediumEditor from 'vue2-medium-editor';
import 'medium-editor/dist/css/medium-editor.css';
// import 'vue2-medium-editor/dist/vue-medium-editor.css';

// Vue.use(MediumEditor);
export default {
    components: {
        MediumEditor
    },
    created() {
        // todo 
        /**
         * color to word
         */
        var testList8 = ["There are only two kinds of people who are really fascinating", "people who know absolutely everything and people who know absolutely nothing"]
        var testList7 = ["It is absurd to divide people into good and bad", "People are whether charming or tedious"]
        var testList6 = ["The public have an insatiable curiosity to know everything", "except what is worth knowing"]
        var testList5 = ["It is only shallow people who require years to get rid of an emotion", "A man who is master of himself can end a sorrow as easily as he can invent a pleasure"]
        var testList4 = ["Men who are trying to do something for the world, are always insufferable", "when the world has done something for them, they are charming"]
        var testList3 = ["I have always been of opinion that hard work is simply the refuge of people who have nothing whatever to do"]
        var testList2 = ["It is always a silly thing to give advice", "but to give good advice is absolutely fatal","I hope you will never fall into that error", "If you do, you will be sorry for it"]
        var testList1 = ["Society often forgives the criminal", "it never forgives the dreamer"]
        
        this.allDataList.push(testList1);
        this.allDataList.push(testList2);
        this.allDataList.push(testList3);
        this.allDataList.push(testList4);
        this.allDataList.push(testList5);
        this.allDataList.push(testList6);
        this.allDataList.push(testList7);
        this.allDataList.push(testList8);
        this.index = 0;
        // this.sentenceList = ['There are two ways of disliking art', "One is to dislike it", "The other is to like it rationally"]
        // this.answerList = ['', '', '']        
        var sList1 = ["Understand ethical wealth creation is possible" , "If you secretly despise wealth","it will elude you"]
        var sList2 = ["Ignore people playing status games" , "They gain status by attacking people playing wealth creation games"]
        this.allDataList = []
        this.allDataList.push(sList1);
        this.allDataList.push(sList2);

    },
    data() {
        return {
            index:-1,
            htmlContent: '<h3>hello</h3>',
            textInput: '',
            answer: 'There are two ways of disliking art',
            message: 'Hello, Vue!',            
            allDataList: [],
            sentenceList: [],
            answerList: []
        };
    },
    watch: {
        index(indexValue) {
            this.sentenceList = this.allDataList[indexValue];    
            let myList = Array(this.sentenceList.length).fill("");
            this.answerList = myList;
        }
    },
    methods: {
        keyMonitor(event) {
            if (event.key === "[") {
                this.goToLast();
            } else if (event.key === "]") {
                this.goToNext();
            } 
            else if (event.key.match(/^[A-Za-z]$/)) {
                console.log("User input: " + event.key);
            } else if (event.key === " ") {
                console.log("hello");
            } 
        },
        logChange(newValue) {
            console.log(this.htmlContent);
            // console.log(newValue);
        },
        goToNext() {
            this.index ++;
            if (this.index == this.allDataList.length) {
                this.index = 0;
            }
        },
        goToLast() {
            this.index --;
            if (this.index == -1) {
                this.index = this.allDataList.length - 1;
            }
        }
    }

};
</script>
  
  