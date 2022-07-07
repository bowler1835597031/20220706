<template>
  <div>
    <input type="text" v-gfocus v-qushuzi="qwe" v-model="aw" />{{ qwe }}
    <!-- v-jujiao -->
    <p v-color="colorStr" @click="colorStr = 'red'">修改文字颜色</p>
  </div>
</template>

<script>
// 目标: 创建 "自定义指令", 让输入框自动聚焦
// 1. 创建自定义指令
// 全局 / 局部
// 2. 在标签上使用自定义指令  v-指令名
// 注意:
// inserted方法 - 指令所在标签, 被插入到dom结构中触发(一次)

// update方法 - 指令对应数据/标签更新时, 此方法执行
export default {
  data() {
    return {
      colorStr: 'green',
      aw: '',
      qwe: '',
    };
  },
  //   directives: {//局部
  //     jujiao: {
  //       inserted(el) {
  //         console.log(el); //指令所在标签
  //         el.focus();
  //       },
  //     },
  //   },
  directives: {
    qushuzi: {
      inserted(el, binding, vnode) {
        console.log(binding.expression);
        el.value = el.value.replace(/[^\d.]/g, '');
        vnode.context[binding.expression] = el.value;
      },
      update(el, binding, vnode) {
        el.value = el.value.replace(/[^\d.]/g, ''); //把所有字母转化为空字符串

        vnode.context[binding.expression] = el.value;
      },
    },
    color: {
      inserted(el, bind) {
        console.log(bind.value);
        el.style.color = bind.value;
      },
      update(el, bind) {
        console.log(bind.value);
        el.style.color = bind.value;
      },
    },
  },
};
</script>

<style></style>
