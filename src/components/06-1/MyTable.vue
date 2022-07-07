<template>
  <div>
    <table border="1">
      <thead>
        <tr>
          <th>序号</th>
          <th>姓名</th>
          <th>年龄</th>
          <th>头像</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="(obj, index) in arr" :key="index">
          <td>{{ index + 1 }}</td>
          <td>
            <slot name="myname" :row="obj">{{ obj.name }}</slot>
          </td>
          <td>
            <slot name="age" :row="obj">{{ obj.name }}</slot>
          </td>
          <td>
            <slot name="toux" :row="obj"> </slot>
          </td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
export default {
  props: {
    arr: Array,
  },
};
</script>
