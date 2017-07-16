<template>
<div id="comment">
    <el-row>
        <el-col :span="4"><div class="grid-content bg-purple"></div><h1></h1></el-col>
        <el-col :span="16">
            <el-form ref="form" :model="form">
                <el-form-item>
                    <el-input
                        type="textarea"
                        :autosize="{ minRows: 2, maxRows: 4}"
                        placeholder="点击发表评论"
                        v-model="form.content">
                    </el-input>
                </el-form-item>
                <el-form-item>
                    <el-button type="primary" @click="onSubmit">发表评论</el-button>
                    <el-button>取消</el-button>
                </el-form-item>
            </el-form>
        </el-col>
        <el-col :span="4"><div class="grid-content bg-purple"></div><h1></h1></el-col>
    </el-row>
</div>
</template>


<script>
export default {
  data() {
    return {
      form: {
          content: ''
        }
    }
  },
  methods: {
      onSubmit() {
        console.log('submit!');
      }
  }

}
</script>