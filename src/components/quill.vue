<template>
  <div class="hello">
    <!-- Include Quill stylesheet -->
    <!-- <link href="https://cdn.quilljs.com/1.0.0/quill.snow.css" rel="stylesheet"> -->
  
    <!-- Create the toolbar container -->
    <div id="toolbar">
      <button class="ql-bold">Bold</button>
      <button class="ql-italic">Italic</button>
    </div>
  
    <!-- Create the editor container -->
    <div id="editor">
      <p>Hello World!</p>
    </div>
  </div>
</template>
<script>
import Quill from 'quill'
export default {
  name: 'Quill',
  mounted() {
    const delta = {  "ops": [
      { "insert": "Hello " },
      { "insert": "World", "attributes": { "bold": true, "color": 'red' } },
      { "insert": "\n" } ]
    }
    var editor = new Quill('#editor', {
      modules: { toolbar: '#toolbar' },
      theme: 'snow'
    });
    editor.setContents(delta)
    console.log('ed', editor)
  }
}
</script>

<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
