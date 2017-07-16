<template>
  <div id="app">
    <el-row>
      <el-col :span="4"><div class="grid-content bg-purple"><h1></h1></div></el-col>
      <el-col :span="16">
        <div class="grid-content bg-purple-light">
           <Nav></Nav>
        </div>
      </el-col>
      <el-col :span="4"><div class="grid-content bg-purple"></div></el-col>
    </el-row>
    <WeeklyReport></WeeklyReport>
    <Comment></Comment>
    
  </div>
</template>

<script>
import Nav from './component/Nav.vue'
import WeeklyReport from './component/WeeklyReport.vue'
import Comment from './component/Comment.vue'

export default {
  data () {
    return {
      msg: 'Use Vue 2.0 Today!'
    }
  },

  components: { Nav, WeeklyReport, Comment},
  methods: {
    startHacking () {
      this.$notify({
        title: 'It Works',
        message: 'We have laid the groundwork for you. Now it\'s your time to build something epic!',
        duration: 6000
      })
    }
    }
}
</script>

<style>
body {
  font-family: Helvetica, sans-serif;
}
.editor-btn{
    margin-top: 20px;
}
</style>
