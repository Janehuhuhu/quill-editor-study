<template>
  <div class="edit_container">
    <h3>quill原生</h3>
    <quill></quill>
    <br>
    <h3>vue-quill-editor</h3>
    <quill-editor 
      v-model="content" 
      ref="myQuillEditor" 
      :options="editorOption" 
      @blur="onEditorBlur($event)" 
      @focus="onEditorFocus($event)"
      @change="onEditorChange($event)">
    </quill-editor>
    <button @click="saveHtml">保存</button>
    </div>  
</template>

<script>
import Quill from './quill.vue'
export default {
  components: { Quill },
  name: 'App',
  data() {
    return {
      content: `<p>hello world</p>`,
      editorOption: {
        // modules 不填存在默认值 
        modules:{
          toolbar:[
            ['bold', 'italic', 'underline', 'strike', 'link'],    //加粗，斜体，下划线，删除线
            ['blockquote', 'code-block'],     //引用，代码块


            [{ 'header': 1 }, { 'header': 2 }],        // 标题，键值对的形式；1、2表示字体大小
            [{ 'list': 'ordered'}, { 'list': 'bullet' }],     //列表
            [{ 'script': 'sub'}, { 'script': 'super' }],   // 上下标
            [{ 'indent': '-1'}, { 'indent': '+1' }],     // 缩进
            [{ 'direction': 'rtl' }],             // 文本方向


            [{ 'size': ['small', false, 'large', 'huge'] }], // 字体大小
            [{ 'header': [1, 2, 3, 4, 5, 6, false] }],     //几级标题


            [{ 'color': [] }, { 'background': [] }],     // 字体颜色，字体背景颜色
            [{ 'font': [] }],     //字体
            [{ 'align': [] }],    //对齐方式


            ['clean'],    //清除字体样式
            ['image','video']    //上传图片、上传视频
          ]
        },
        theme:'snow'
      }
     }
  },
  computed: {
    editor() {
      return this.$refs.myQuillEditor.quill;
    },
  },
  methods: {
    onEditorReady(editor) { // 准备编辑器
      console.log('准备好了', editor)
    },
    onEditorBlur(){
      console.log('失去焦点事件')
    }, // 失去焦点事件
    onEditorFocus(){
      console.log('获得焦点事件')
    }, // 获得焦点事件
    onEditorChange(){
      console.log('内容改变事件')
    }, // 内容改变事件
    saveHtml(event){
      console.log(event, this.content);
    }
  }
}
</script>