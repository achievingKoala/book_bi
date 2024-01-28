<template>
  <div class="about">
    <h1>This is an about page</h1>
    <medium-editor :text="styledHtmlContent" custom-tag="div" v-model="htmlContent" :options="{ toolbar: { buttons: ['bold', 'italic', 'underline', 'anchor', 'h2', 'h3', 'quote'] } }"></medium-editor>

  </div>
</template>

<script>
  import MediumEditor from 'vue2-medium-editor';
  import 'medium-editor/dist/css/medium-editor.css';
  
  export default {
    data() {
      return {
        htmlContent: 'dafdasf <h3>adfa</h3> sadfaaa',
      };
    },
    computed: {
      styledHtmlContent() {
        console.log(this.htmlContent)
        let words = this.htmlContent.split(' ');
        if (words.length > 1) {
          words[1] = `<span class="green">${words[1]}</span>`;
        }
        return words.join(' ');
      }
    },
    components: {
      MediumEditor
    },
  };
</script>
<style scoped>
.green {
  color: green;
}
</style>