<template
  ><div>
    <MyTable :arr="list">
      <template v-slot:myname="scope">
        <input type="text" v-model="scope.row.name" />
      </template>

      <template v-slot:age="scope">
        <input type="text" v-model="scope.row.age"
      /></template>

      <template #toux="scope">
        <a v-if="scope.row.type == 0" :href="scope.row.headImgUrl">{{
          scope.row.headerImgUrl
        }}</a>
        <img
          v-else-if="scope.row.type == 1"
          :src="scope.row.headImgUrl"
          alt=""
        />
        <div v-else>{{ scope.row.headImgUrl }}</div>
      </template>
    </MyTable>
  </div>
</template>

<script>
import MyTable from '../components/06-1/MyTable.vue';
export default {
  components: {
    MyTable,
  },
  data() {
    return {
      list: [
        {
          id: 100,
          name: '小传同学',
          age: 18,
          headImgUrl:
            'http://yun.itheima.com/Upload/./Images/20210303/603f2d2153241.jpg',
          type: 0, // 0 显示成a标签
        },
        {
          id: 101,
          name: '小黑同学',
          age: 25,
          headImgUrl:
            'http://yun.itheima.com/Upload/./Images/20210304/6040b101a18ef.jpg',
          type: 1, // 1 显示成图片
        },
        {
          id: 102,
          name: '智慧同学',
          age: 21,
          headImgUrl:
            'http://yun.itheima.com/Upload/./Images/20210302/603e0142e535f.jpg',
          type: 1, // 1 显示成图片
        },
        {
          id: 103,
          name: '智慧同学',
          age: 21,
          headImgUrl:
            'http://yun.itheima.com/Upload/./Images/20210302/603e0142e535f.jpg',
          type: 2, // 2 显示成文本
        },
      ],
    };
  },
};
</script>

<style></style>
