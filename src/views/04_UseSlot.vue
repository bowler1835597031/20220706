<template>
  <div id="container">
    <div id="app">
      <h3>案例：折叠面板</h3>
      <MyPanel>
        <template v-slot:title>
          <h4>案例：折叠面板45141</h4>
        </template>
        <template v-slot:content>
          <img src="../assets/mm.gif" alt="" />
        </template>
      </MyPanel>
    </div>
  </div>
</template>

<script>
import MyPanel from '../components/04/Panel.vue';
export default {
  components: {
    MyPanel,
  },
};
</script>

<style>
#app {
  width: 400px;
  margin: 20px auto;
  background-color: #fff;
  border: 4px solid blueviolet;
  border-radius: 1em;
  box-shadow: 3px 3px 3px rgba(0, 0, 0, 0.5);
  padding: 1em 2em 2em;
}
</style>
