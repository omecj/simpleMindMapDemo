<template>
  <div class="simpleMindMap">
    <div id="mindMapContainer"></div>
  </div>
</template>

<script setup>
import {onMounted, ref} from 'vue';
import MindMap from "simple-mind-map";
import {cloneDeep} from 'lodash'

const activeNodes = ref([])

// eslint-disable-next-line no-unused-vars
const addNote = () => {
  activeNodes.value.forEach(node => {
    node.setNote("哈哈123456🚅🚕🚎🚎😊👍😍🤦‍♀️")
  })
}

onMounted(() => {
  // eslint-disable-next-line no-unused-vars
  const mindMap = new MindMap({
    el: document.getElementById("mindMapContainer"),
    data: {
      data: {
        text: "根节点",
        note: "前提：已安装node.js和npm的国内镜像cnpm\n" +
            "1、先下载安装npm\n" +
            "2、全局安装cnpm\n" +
            "\n" +
            "npm install -g cnpm --registry=https://registry.npm.taobao.org\n" +
            "3、全局安装vue-cli\n" +
            "\n" +
            "cnpm install --global vue-cli\n" +
            "或\n" +
            "cnpm intall vue-cli -g\n" +
            "查看是否安装node\n" +
            "node -v\n" +
            "查看是否安装npm\n" +
            "npm -v\n" +
            "查看是否安装vue-cli\n" +
            "npm list\n" +
            "4、初始化vue项目\n" +
            "方法一：在该目录下初始化项目\n" +
            "\n" +
            "vue init webpack\n" +
            "方法二：在该目录下新建项目\n" +
            "\n" +
            "\n" +
            "vue init webpack 'mytest'"
      },
      children: [],
    },
  });
  mindMap.on('node_active', (node, nodeList) => {
    activeNodes.value = cloneDeep(nodeList)
  })

})
</script>

<style lang='scss' scoped>
.simpleMindMap {
  width: 100%;
  height: 100%;
  padding: 0;
  box-sizing: border-box;
  background-color: #fff;
  position: relative;

  #mindMapContainer {
    width: 100%;
    height: 100%;
  }
}
</style>