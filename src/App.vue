<template>
  <div>
    <!-- <h1>1. 动态dynamic组件使用</h1>
    <component :is="comName"></component>
    <UseDynamic></UseDynamic>
    <hr />
    <h1>2. 组件缓存</h1>
    <UseDynamic1></UseDynamic1>
    <hr />
    <h1>3. 组件-插槽</h1> -->
    <!-- <Panel></Panel> -->
    <!-- <UseSlot></UseSlot>
    <hr />
    <h1>4. 组件-具名插槽</h1>
    <UseSlot1></UseSlot1>
    <hr />
    <h1>5. 组件-作用域插槽</h1>
    <UseSlot2></UseSlot2>
    <hr />
    <h1>6. 作用域插槽-使用场景</h1>
    <p>组件内标签可以随意定义和数据使用</p>
    <UseSlot3></UseSlot3>
    <hr /> -->
    <UseSlot4></UseSlot4>
    <h1>7. 自定义指令</h1>
  </div>
</template>

<script>
import MyTest from './components/compent.vue';
import UseDynamic from './views/01_UseDynamic.vue';
import UseDynamic1 from './views/02_UseDynamic.vue';
import Panel from './components/Panel.vue';
import UseSlot from './views/03_UseSlot.vue';
import UseSlot1 from './views/04_UseSlot.vue';
import UseSlot2 from './views/05_UseSlot.vue';
import UseSlot3 from './views/06_UseTable.vue';
import UseSlot4 from './views//06_1UseTable.vue';
export default {
  components: {
    MyTest,
    UseDynamic,
    UseDynamic1,
    Panel,
    UseSlot,
    UseSlot1,
    UseSlot2,
    UseSlot3,
    UseSlot4,
  },
  data() {
    return {
      comName: 'MyTest',
    };
  },
};
</script>

<style></style>
