<template>
    <div>
        <!-- Your component's template -->
        <!-- <textarea cols= "100" type="text" v-model="textInput" :style="{
            color: textInput === answer ? 'green' : 'blue',
            fontSize: 'larger', width: '300px',
            height: '200px' 
        }"></textarea> -->
        <!-- <div v-html="htmlContent"></div> -->
        <!-- <textarea :value="htmlContent"></textarea> -->
        <!-- <quill-editor v-model="htmlContent"  /> -->
        <!-- <medium-editor   /> -->
        
        
        <el-button ref="myButton">哈哈哈</el-button>

        <!-- <textarea> <h3>hello</h3> 009 wfw3 <span style="color: green;">9</span></textarea> -->
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
        <el-button>last</el-button>
        <el-button>next</el-button>
        <div style="border: 1px solid #CBCBCB;height: 200px;width: 400px" contenteditable="true" >
            <span contenteditable="false" >投入：</span><span style="color: red">500</span>
        </div>
    </div>
</template>
  
<script>
import { quillEditor } from 'vue-quill-editor';
import 'quill/dist/quill.core.css';
import 'quill/dist/quill.snow.css';
import 'quill/dist/quill.bubble.css';

// import Vue from 'vue';
import MediumEditor from 'vue2-medium-editor';
import 'medium-editor/dist/css/medium-editor.css';
// import 'vue2-medium-editor/dist/vue-medium-editor.css';

// Vue.use(MediumEditor);
export default {
    components: {
        MediumEditor

    },
    created() {
        console.log('---->', this.$refs.myButton)
        // this.onContentChange()
        // todo 
        /**
         * color to word
         */
        var testList1 = ["There are only two kinds of people who are really fascinating", "people who know absolutely everything and people who know absolutely nothing"]
        var testList1 = ["It is absurd to divide people into good and bad", "People are whether charming or tedious"]
        var testList1 = ["The public have an insatiable curiosity to know everything", "except what is worth knowing"]
        var testList1 = ["It is only shallow people who require years to get rid of an emotion", "A man who is master of himself can end a sorrow as easily as he can invent a pleasure"]
        var testList1 = ["Men who are trying to do something for the world, are always insufferable", "when the world has done something for them, they are charming"]
        var testList1 = ["I have always been of opinion that hard work is simply the refuge of people who have nothing whatever to do"]
        
        var item2 = ["There", "are", "two", "ways", "of", "disliking", "art", "One", "is"]
        // this.sentenceList = ['There are two ways of disliking art', "One is to dislike it", "The other is to like it rationally"]
        // this.answerList = ['', '', '']        
        let myList = Array(testList1.length).fill("");
        this.answerList = myList;
        this.sentenceList = testList1;
    },
    data() {
        return {
            htmlContent: 'hello',
            textInput: '',
            answer: 'There are two ways of disliking art',
            message: 'Hello, Vue!',
            sentenceList: [],
            answerList: []
        };
    },
    watch: {
        htmlContent(newValue) {
            console.log(newValue);
        },
    },
    methods: {
        goToNext() {
    
        }
    }

};
</script>
  
  