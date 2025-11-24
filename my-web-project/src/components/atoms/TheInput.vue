<template>
  <div class="input-container">
    <label v-if="label" :for="id" class="input-label">{{ label }}</label>
    <input
      :id="id"
      :type="type"
      :placeholder="placeholder"
      :value="modelValue"
      @input="$emit('update:modelValue', $event.target.value)"
      class="text-input"
    />
    <slot name="icon"></slot>
  </div>
</template>

<script>
export default {
  name: 'TheInput',
  props: {
    id: { type: String, required: true },
    label: { type: String, default: '' },
    type: { type: String, default: 'text' },
    placeholder: { type: String, default: '' },
    modelValue: { type: [String, Number], default: '' }
  },
  emits: ['update:modelValue']
};
</script>

<style scoped>
.input-container {
  position: relative;
  margin-bottom: 15px;
  background-color: #f3f3f3; /* Arka plan rengi */
  border-radius: 4px;
}

.input-label {
  position: absolute;
  top:20px; /* Yerleşimi formdaki gibi hizalamak için */
  left: 10px;
  font-size: 15px;
  color: #666;
  pointer-events: none;
  z-index: 1;
}

/* Stil verilen görüntüdeki giriş kutularına çok benziyor */
.text-input {
  width:512px;
  padding: 25px 10px 10px 10px; /* Label için üst boşluğu artır */
  font-size: 16px;
  border: none; 
  background-color: transparent;
  outline: none;
  color: #333;
  box-sizing: border-box;
}

.text-input:focus{
  border:0.5px solid black;
  background-color: white;
}

.input-labal:focus{
  background-color: white;
  display:none;
  width: auto;
  position:absolute;
  top:-5px;
}
</style>