<template>
    <input 
      :type="type"
      class="form-control m-input" 
      :placeholder="placeholder"
      v-model="inputValue"
      @input="inputChange"
    />
</template>
<script>
/**
 * app-input sử dụng cho các component input kiểu : text, email, number
 */
export default {
  name: "app-input",
  props: {
    /**
     * @Model
     */
    value: [String, Number],
    /**
     * Kiểu giá trị của input
     */
    type: {
      type: String
    },
    /**
     * PlaceHolder
     */
    placeholder: String,
    name: {
      type: String,
      required: true
    }
  },
  // $_veeValidate: {
  // 	// name() {
  // 	// 	return this.name;
  // 	// },
  // 	value() {
  // 		return this.inputValue;
  // 	}
  // },
  data() {
    return {
      inputValue: this.value
    };
  },
  methods: {
    /**
     * Hàm được gọi khi giá trị của input được thay đổi từ bên trong
     */
    inputChange() {
      this.$emit("input", this.inputValue);
    }
  },
  mounted() {}
};
</script>
