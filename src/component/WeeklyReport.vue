<template>
  <div class="weekly-report-content">
      <el-row>
          <el-col :span="4"><div class="grid-content bg-purple"></div><h1></h1></el-col>
          <el-col :span="16">
              <!--<el-button @click.native="startHacking" type="primary" icon="edit">写周报</el-button>-->
              <el-tag type="gray">本周周报</el-tag>
          </el-col>
          <el-col :span="4"><div class="grid-content bg-purple"></div><h1></h1></el-col>
      </el-row>
  <el-row>
    <el-col :span="4"><div class="grid-content bg-purple"></div><h1></h1></el-col>
    <el-col :span="16">
      <quill-editor ref="myTextEditor" v-model="content" :config="editorOption">
      </quill-editor>
      <el-button class="editor-btn" type="primary" @click="submit" :loading="false">发布周报</el-button>
    </el-col>
    <el-col :span="4"><div class="grid-content bg-purple"></div></el-col>
  </el-row>
  </div>
</template>

<script>
import { quillEditor } from 'vue-quill-editor';

  export default {
  data () {
    return {
      msg: 'Use Vue 2.0 Today!',
      content: '<p>Hello BBK</p>',
      editorOption: {
        debug: 'info',
        modules: {
          toolbar: '#toolbar'
        },
        placeholder: 'Compose an epic...',
        readOnly: true,
        theme: 'snow'
      }
    }
  },

  components: {quillEditor},
  methods: {
    startHacking () {
      this.$notify({
        title: 'It Works',
        message: 'We have laid the groundwork for you. Now it\'s your time to build something epic!',
        duration: 6000
      })
    },
    onEditorChange({ editor, html, text }) {
                this.content = html;
            },
            submit(){
                console.log(this.content);
                this.$message.success('发布成功！');
            }
    },
    computed: {
      editor() {
          return this.$refs.myTextEditor.quillEditor;
      }
    }
}
</script>

<style>
.el-row {
    margin-bottom: 20px;
    &:last-child {
      margin-bottom: 0;
    }
}
.weekly-report-content {
  padding: 30px 0 0 0;
  margin-top: 40px;
}
.ql-container .ql-editor {
  min-height: 15em;
  padding-bottom: 1em;
  max-height: 20em;
}
</style>