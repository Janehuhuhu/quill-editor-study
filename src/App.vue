<template>
  <div class="edit_container">
    <h1>quill 样例</h1>
    <quill-demo></quill-demo>
    <h1>drag 样例</h1>
    <drag-demo></drag-demo>
  </div>  
</template>

<script>
import QuillDemo from './components/quill-demo.vue'
import DragDemo from './components/drag-demo.vue'
export default {
  components: { QuillDemo, DragDemo },
  name: 'App',
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>