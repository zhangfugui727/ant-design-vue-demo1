<template>
  <a-space direction="vertical">
    <a-button @click="showValue">显示值</a-button>
    <a-date-picker v-model:value="value1" valueFormat="YYYY-MM-DD" />
    <a-date-picker v-model:value="value2" valueFormat="YYYY-MM-DD HH:mm:SS" />
    <a-date-picker v-model:value="formValue.date" valueFormat="YYYY-MM-DD" />
    <a-date-picker v-model:value="formValue.date1" valueFormat="YYYY-MM-DD" />
    <a-range-picker v-model:value="value3" />
    <a-week-picker v-model:value="value4" placeholder="Select week" />
  </a-space>
</template>
<script>
import { defineComponent, ref, unref, reactive, toRaw } from "vue";
import moment from "moment";
export default defineComponent({
  setup() {
    let formValue = reactive({
      date: moment("2021-01-05"),
      date1: undefined,
    });

    return {
      value1: ref(moment("2021-01-05")),
      value2: ref(),
      value3: ref([]),
      value4: ref(),
      formValue,
    };
  },
  methods: {
    showValue() {
      alert(JSON.stringify(unref(this.value1)));
      alert(JSON.stringify(unref(this.value2)));
      alert(JSON.stringify(toRaw(this.formValue)));
    },
  },
});
</script>