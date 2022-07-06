<template>
  <div>
    <MyHeader
      title="购物车案例"
      backgroundColor="skyblue"
      color="write"
    ></MyHeader>
    <MyGoods v-for="item in list" :key="item.id" :obj="item"></MyGoods>
    <!-- :obj的obj与子的props的obj保持一致，父传子 -->
    <MyFooter></MyFooter>
  </div>
</template>

<script>
// 目标: 项目初始化 - 静态页面
// 1. 创建项目, 下包, 引入bs样式
// 2. 拆分需求组件, 创建 - 分别标签+样式
// 3. App.vue上显示, 微调样式(上下内边距)

// 目标: 数据 铺设到MyGoods组件上
// 1. 数据在data保存一下(页面只能用data里值)
// 2. 页面v-for循环MyGoods组件
// 3. 分别传入obj数据对象 (一对一关系)
// 4. 内部使用数据对象值渲染到标签上
import MyHeader from './components/MyHeader.vue';
import MyGoods from './components/MyGoods.vue';
import MyFooter from './components/MyFooter.vue';
export default {
  components: {
    MyHeader,
    MyGoods,
    MyFooter,
  },
  created() {
    //在网站里取信息
    this.$axios({
      url: '/api/cart',
    }).then((res) => {
      console.log(res.data.list);
      this.list = res.data.list; //创建list属性接网站里的值
    });
  },
  data() {
    return {
      list: [], //建，created接
    };
  },
};
</script>

<style scoped>
.main {
  padding-top: 45px;
  padding-bottom: 50px;
}
</style>
