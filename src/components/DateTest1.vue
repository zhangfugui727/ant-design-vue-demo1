<template>
  <a-space direction="vertical">
    <a-button @click="getValue">test</a-button>
    <a-date-picker
      show-time
      placeholder="Select Time"
      @change="onChange"
      @ok="onOk"
    />
    valueFormat="YYYY-MM-DD HH:mm:ss"
    <a-range-picker
      :show-time="{ format: 'HH:mm' }"
      format="YYYY-MM-DD HH:mm"
      :placeholder="['Start Time', 'End Time']"
      v-model:value="value"
      @change="onChange"
      @ok="onOk"
    />
  </a-space>
</template>
<script>
import { defineComponent, ref } from "vue";
export default defineComponent({
  setup() {
    const onChange = (value, dateString) => {
      console.log("Selected Time: ", value);
      console.log("Formatted Selected Time: ", dateString);
    };

    const onOk = (value) => {
      console.log("onOk: ", value);
    };

    return {
      value: ref(),
      onChange,
      onOk,
    };
  },
  methods: {
    getValue() {
      console.log("onOk: ", this.value);
      alert(JSON.stringify(this.value[0]));
    },
  },
});
</script>