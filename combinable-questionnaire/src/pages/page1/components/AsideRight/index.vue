<template>
  <el-aside
    width="200px"
    class="questionnaire__aside--right">
    <div
      v-for="(item, index) in reslist"
      :key="index">
      <div
        class="questionnaire__res-key">
        {{item.keyName}}
      </div>
      <div
        class="questionnaire__res-value">
        {{item.value === '' ? '未填写' : item.value}}
      </div>
    </div>
  </el-aside>
</template>

<script>
export default {
  props: {
    // 接收表单结果
    res: {
      default: () => ({})
    }
  },
  computed: {
    // 处理数据格式
    reslist () {
      return Object.keys(this.res).map(keyName => ({
        keyName,
        value: this.res[keyName]
      }))
    }
  }
}
</script>
