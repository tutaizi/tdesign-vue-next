<template>
  <div class="tdesign-demo-upload">
    <div style="width: 350px">
      <!-- abridgeName 省略中间文本，首尾保留的文本字符 -->
      <t-upload
        v-model="files"
        action="https://service-bv448zsw-1257786608.gz.apigw.tencentcs.com/api/upload-demo"
        :abridge-name="[8, 6]"
        theme="file-input"
        placeholder="未选择文件"
        @fail="handleFail"
      ></t-upload>
    </div>
  </div>
</template>
<script setup>
import { ref } from 'vue';
import { MessagePlugin } from 'tdesign-vue-next';

const files = ref([]);

const handleFail = ({ file }) => {
  MessagePlugin.error(`文件 ${file.name} 上传失败`);
};
</script>
