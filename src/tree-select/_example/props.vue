<template>
  <div class="tdesign-tree-select-base">
    <t-tree-select
      v-model="value"
      :data="options"
      clearable
      placeholder="请选择"
      :popup-props="popupProps"
      :tree-props="treeProps"
    />
  </div>
</template>
<script setup>
import { ref } from 'vue';

const options = [
  {
    name: '广东省',
    pinyin: 'guangdong',
    children: [
      {
        name: '广州市',
        pinyin: 'guangzhou',
      },
      {
        name: '深圳市',
        pinyin: 'shenzhen',
      },
    ],
  },
  {
    name: '江苏省',
    pinyin: 'jiangsu',
    children: [
      {
        name: '南京市',
        pinyin: 'nanjing',
      },
      {
        name: '苏州市',
        pinyin: 'suzhou',
      },
    ],
  },
];

const value = ref('shenzhen');

const popupProps = {
  overlayStyle: {
    width: '500px',
  },
};

const treeProps = {
  keys: {
    label: 'name',
    value: 'pinyin',
    children: 'children',
  },
};
</script>
<style scoped>
.tdesign-tree-select-base {
  width: 300px;
  margin: 0 20px;
}
</style>
