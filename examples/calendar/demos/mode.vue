<template>
  <div>
    <div style="margin: 12px 0">
      <label>可以在组件外切换成：</label>
      <t-select v-model="mode" class="demo-select-base">
        <t-option v-for="item in options" :key="item.value" :value="item.value" :label="item.label" />
      </t-select>
    </div>
    <t-calendar :mode="mode" />
  </div>
</template>

<script>
import { defineComponent, ref } from 'vue';

const options = [
  { value: 'month', label: '日历' },
  { value: 'year', label: '月历' },
];

export default defineComponent({
  setup() {
    const mode = ref('year');
    return {
      mode,
      options,
    };
  },
});
</script>

<style scoped>
.demo-select-base {
  width: 200px;
  display: inline-block;
  margin: 0 10px 0 0;
}
</style>
