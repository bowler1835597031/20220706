<template>
  <!-- 底部 -->
  <div class="my-footer">
    <!-- 全选 -->
    <div class="custom-control custom-checkbox">
      <input
        type="checkbox"
        class="custom-control-input"
        id="footerCheck"
        v-model="isAll"
      />
      <label class="custom-control-label" for="footerCheck">全选</label>
    </div>
    <!-- 合计 -->
    <div>
      <span>合计:</span>
      <span class="price">￥{{ allSum }}</span>
    </div>
    <!-- 按钮 -->
    <button type="button" class="footer-btn btn btn-primary">
      结算 ({{ allCount }})
    </button>
  </div>
</template>

<script>
export default {
  computed: {
    isAll: {
      set(val) {
        // val就是关联表单的值(true/false) 全选选中状态
        this.$parent.list.forEach((ele) => {
          ele.goods_state = val;
        });
      },
      get() {
        // 查找小选框关联的属性有没有不符合勾选的条件
        // 直接原地false
        return this.$parent.list.every((ele) => ele.goods_state === true);
      },
    },
    allCount() {
      //只统计选中的数据
      return this.$parent.list.reduce((sum, ele) => {
        if (ele.goods_state === true) {
          sum += ele.goods_count;
        }
        return sum;
      }, 0);
    },
    allSum() {
      return this.$parent.list.reduce((sum, ele) => {
        if (ele.goods_state === true) {
          sum = sum + ele.goods_count * ele.goods_price;
        }
        return sum;
      }, 0);
    },
  },
};
</script>

<style lang="less" scoped>
.my-footer {
  position: fixed;
  z-index: 2;
  bottom: 0;
  width: 100%;
  height: 50px;
  border-top: 1px solid #ccc;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 0 10px;
  background: #fff;

  .price {
    color: red;
    font-weight: bold;
    font-size: 15px;
  }
  .footer-btn {
    min-width: 80px;
    height: 30px;
    line-height: 30px;
    border-radius: 25px;
    padding: 0;
  }
}
</style>
